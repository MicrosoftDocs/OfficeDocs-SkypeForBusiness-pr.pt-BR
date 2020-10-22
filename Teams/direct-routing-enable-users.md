---
title: Habilitar usuários para roteamento direto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como habilitar o roteamento direto do sistema de usuários do Microsoft Phone System.
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655478"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Habilite os usuários para roteamento direto, voz e correio de voz

Este artigo descreve como habilitar usuários para o roteamento direto do sistema telefônico.  Esta é a etapa 2 das seguintes etapas para configurar o roteamento direto:

- Etapa 1. [Conectar o SBC com o sistema Microsoft Phone e validar a conexão](direct-routing-connect-the-sbc.md) 
- **Etapa 2. Habilite os usuários para roteamento direto, voz e correio de voz**   (este artigo)
- Etapa 3. [Configurar roteamento de voz](direct-routing-voice-routing.md)
- Etapa 4. [Converter números em um formato alternativo](direct-routing-translate-numbers.md) 


Para obter informações sobre todas as etapas necessárias para configurar o roteamento direto, consulte [Configurar o roteamento direto](direct-routing-configure.md).

Quando estiver pronto para habilitar os usuários para roteamento direto, siga estas etapas: 

1. Crie um usuário no Microsoft 365 ou no Office 365 e atribua uma licença do sistema telefônico. 
2. Certifique-se de que o usuário esteja hospedado no Skype for Business online. 
3. Configurar o número de telefone e habilitar o Enterprise Voice e correio de voz. 
4. Atribuir o modo apenas Teams aos usuários.

## <a name="create-a-user-and-assign-the-license"></a>Criar um usuário e atribuir a licença 

Há duas opções para criar um novo usuário no Microsoft 365 ou no Office 365. No entanto, a Microsoft recomenda que sua organização escolha uma opção para evitar problemas de roteamento: 

- Crie o usuário no Active Directory local e sincronize o usuário com a nuvem. Confira [integrar seus diretórios locais com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
- Crie o usuário diretamente no centro de administração do Microsoft 365. Consulte [Adicionar usuários individualmente ou em massa ao Microsoft 365 ou ao Office 365-ajuda para administradores](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Se sua implantação do Skype for Business online existir com o Skype for Business 2015 ou o Lync 2010 ou 2013 local, a única opção com suporte é criar o usuário no Active Directory local e sincronizar o usuário com a nuvem (opção 1). 

Para obter informações sobre os requisitos de licença, consulte [Licenciamento e outros requisitos](direct-routing-plan.md#licensing-and-other-requirements) no [Roteamento direto do plano](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>Certifique-se de que o usuário esteja hospedado online e o número de telefone não esteja sendo sincronizado no local (aplicável para usuários habilitados do Skype for Business Server Enterprise que estão sendo migrados para o roteamento direto do Teams)

O roteamento direto exige que o usuário seja hospedado online. Você pode verificar a aparência do parâmetro RegistrarPool, que precisa ter um valor no domínio infra.lync.com. O parâmetro OnPremLineUriManuallySet também deve ser definido como true. Isso é conseguido Configurando o número de telefone e habilitando o correio de voz e o correio de voz corporativos usando o Skype for Business online PowerShell.

1. Conecte uma sessão do PowerShell do Skype for Business online.

2. Execute o comando: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Em caso de OnPremLineUriManuallySet ser definido como false e LineUri for preenchido com um número de telefone <E. 164>, limpe os parâmetros usando o Shell de gerenciamento do Skype for Business local, antes de configurar o número de telefone usando o Skype for Business online PowerShell. 

1. No Shell de gerenciamento do Skype for Business, execute o comando: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   Depois que as alterações tiverem sido sincronizadas com o Office 365, a saída esperada `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` seria:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configurar o número de telefone e habilitar o Enterprise Voice e correio de voz 

Depois de criar o usuário e atribuir uma licença, a próxima etapa é configurar o número de telefone do usuário e o correio de voz. 

Para adicionar o número de telefone e habilitar o correio de voz:
 
1. Conecte uma sessão do PowerShell do Skype for Business online. 

2. Execute o comando: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    Por exemplo, para adicionar um número de telefone para o usuário "Spencer baixo", digite o seguinte: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    Se os usuários "Spencer baixo" e "Stacy Quinn" compartilharem o mesmo número base com extensões exclusivas, insira o seguinte
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    É recomendável, mas não obrigatório, que o número de telefone usado é configurado como um número de telefone E. 164 completo com código de país. Ele tem suporte para configurar números de telefone com extensões que serão usadas para pesquisar usuários quando a pesquisa do número base retornar mais de um resultado. Isso permite que as empresas configurem números de telefone com o mesmo número base e ramais exclusivos. Para que a pesquisa seja bem-sucedida, o convite deve incluir o número completo com extensão da seguinte maneira:
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > Se o número de telefone do usuário for gerenciado localmente, use o Shell de gerenciamento do Skype for Business local ou o painel de controle para configurar o número de telefone do usuário. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Configurar o envio de chamadas diretamente para o correio de voz

O roteamento direto permite encerrar a chamada para um usuário e enviá-la diretamente ao correio de voz do usuário. Se você quiser enviar a chamada diretamente para o correio de voz, anexe opaco = App: correio de voz ao cabeçalho URI da solicitação. Por exemplo, "SIP: user@yourdomain. com; opaco = App: correio de voz". Nesse caso, o usuário do Teams não receberá a notificação de chamada, a chamada será conectada diretamente ao correio de voz do usuário.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Atribuir o modo apenas Teams aos usuários para garantir chamadas no Microsoft Teams

O roteamento direto requer que os usuários estejam no modo somente Teams para garantir que as chamadas de entrada sejam feitas no cliente do teams. Para colocar usuários no modo somente Teams, atribua a eles a instância "UpgradeToTeams" de TeamsUpgradePolicy. Para obter mais informações, consulte [diretrizes de atualização para administradores de ti](upgrade-to-teams-on-prem-overview.md). Se sua organização usa o Skype for Business Server ou o Skype for Business Online, consulte o artigo a seguir para obter informações sobre interoperabilidade entre o Skype e o Teams: [migração e interoperabilidade com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
