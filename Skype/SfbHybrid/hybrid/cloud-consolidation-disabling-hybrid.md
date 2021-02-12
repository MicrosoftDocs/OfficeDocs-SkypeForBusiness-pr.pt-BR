---
title: Desabilitar a migração híbrida para concluir a nuvem
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui etapas detalhadas para desabilitar o híbrido como parte da consolidação na nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: 93aad1ea230d9edbb81673a3ddabc7088b06d422
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277251"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Desabilitar a migração híbrida para concluir a nuvem

Depois de mover todos os usuários do local para a nuvem, você poderá desativar a implantação do Skype for Business local. Além de remover qualquer hardware, uma etapa crítica é separar logicamente essa implantação local do Microsoft 365 ou Office 365 desabilitando a implantação híbrida. A desabilitação híbrida consiste em 3 etapas:

1. Atualize os registros DNS para apontar para o Microsoft 365 ou Office 365.

2. Desabilite o domínio dividido na organização do Microsoft 365 ou Office 365.

3. Desabilite a capacidade no local de se comunicar com o Microsoft 365 ou o Office 365.

Essas etapas devem ser realizadas juntas como uma unidade. Os detalhes são fornecidos abaixo. Além disso, são fornecidas diretrizes para gerenciar números de telefone para usuários migrados depois que a implantação local é desconectada.

Depois que essas etapas são concluídas, os servidores locais do Skype for Business não são mais usados, e esses servidores podem ser reempresados.

> [!Important] 
>Você deve continuar a permitir que os atributos msRTCSIP no Active Directory sincronizem por meio do Azure AD Connect no Azure AD.  Não limpe nenhum desses atributos, a menos que direcionado pelo Suporte.  Não execute Disable-CsUser no ambiente local. Se você precisar modificar o endereço SIP de um usuário, faça isso em seu Active Directory local e deixe essa alteração sincronizar com o Azure AD por meio do Azure AD Connect, conforme descrito abaixo. Da mesma forma, se você precisar alterar um número de telefone e o LineURI do usuário já estiver definido no local, modifique-o no Active Directory local.
>Limpar os atributos msRTCSIP locais depois de migrar do local pode resultar em perda de serviço para os usuários!


1.  *Atualize o DNS para apontar para o Microsoft 365 ou Office 365.*
O DNS externo da organização para a organização local precisa ser atualizado para que os registros do Skype for Business apontem para o Microsoft 365 ou Office 365 em vez da implantação local. Especificamente:

    |Tipo de registro|Nome|TTL|Valor|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync. <span> com|
    |CNAME| sip|    3600|   sipdir.online.lync. <span> com|
    |CNAME| meet|   3600|   webdir.online.lync. <span> com|
    |CNAME| dialin  |3600|  webdir.online.lync. <span> com|

    Além disso, os registros CNAME para reunir ou discar (se presente) podem ser excluídos. Por fim, todos os registros DNS do Skype for Business em sua rede interna devem ser removidos.

    > [!Note] 
    > Em casos raros, a alteração do DNS de apontar para o Office 365 local para sua organização pode fazer com que a federação com algumas outras organizações pare de funcionar até que outra organização atualize sua configuração de federação:
    >
    > - Todas as organizações federadas que estão usando o modelo de Federação Direta mais antigo (também conhecido como Servidor de Parceiros Permitidos) precisarão atualizar suas entradas de domínio permitidas para que sua organização remova o FQDN do proxy. Esse modelo de federação herdado não se baseia em registros SRV DNS, portanto, essa configuração ficará desa datada depois que sua organização for para a nuvem.
    > 
    > - Qualquer organização federada que não tenha um provedor de hospedagem habilitado para sipfed.online.lync. <span> com precisará atualizar sua configuração para habilitar isso. Essa situação só será possível se a organização federada for puramente local e nunca tiver federado com qualquer locatário híbrido ou online. Nesse caso, a federação com essas organizações não funcionará até que habilitam seu provedor de hospedagem.
    >
    > Se você suspeitar que qualquer um de seus parceiros federados possa estar usando a Federação Direta ou não tiver federado com qualquer organização online ou híbrida, sugerimos que você envie uma comunicação sobre isso enquanto se prepara para concluir sua migração para a nuvem.


2.  *Desabilite o espaço de endereço SIP compartilhado na organização do Microsoft 365 ou office 365.*
O comando a seguir precisa ser feito em uma janela do PowerShell do Skype for Business Online.

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *Desabilite a capacidade no local de se comunicar com o Microsoft 365 ou o Office 365.*  
O comando a seguir precisa ser feito em uma janela do PowerShell local:

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Gerenciar endereços SIP e números de telefone para usuários que foram migrados do local

Os administradores podem gerenciar usuários que foram movidos anteriormente de um Skype for Business Server local para a nuvem, mesmo após a implantação local ser desativada. Se você quiser fazer alterações no endereço SIP de um usuário ou no URI de Linha de um usuário (e o endereço SIP ou o URI da Linha já estiver definido no Active Directory local), você deve fazer isso no Active Directory local e permitir que os valores fluam para o Azure AD. Isso NÃO requer o Skype for Business Server local. Em vez disso, você pode modificar esses atributos diretamente no Active Directory local, usando o snap-in MMC usuários e computadores do Active Directory ou usando o PowerShell. Se você estiver usando o snap-in do MMC, abra a página de propriedades do usuário, clique na guia Editor de Atributos e encontre os atributos apropriados para modificar:

- Para modificar o endereço SIP de um usuário, modifique o `msRTCSIP-PrimaryUserAddress` . Além disso, se o `ProxyAddresses` atributo contiver um valor SIP, atualize esse valor SIP para corresponder ao novo valor de `msRTCSIP-PrimaryUserAddress` . Se ele não tiver um valor SIP, você poderá deixá-lo em branco.

- Para modificar o número de telefone de um usuário, `msRTCSIP-Line` *modifique se ele já tiver um valor.*

  ![Ferramenta de usuários e computadores do Active Directory](../media/disable-hybrid-1.png)
  
Se o usuário originalmente não tinha um valor para o local antes da movimentação, você pode modificar o LineURI usando o parâmetro - no `LineURI` `onpremLineUri` [cmdlet Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) no módulo PowerShell do Skype for Business Online.


## <a name="see-also"></a>Confira também

[Consolidação na nuvem para o Teams e o Skype for Business](cloud-consolidation.md)
