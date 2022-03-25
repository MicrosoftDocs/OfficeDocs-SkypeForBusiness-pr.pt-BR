---
title: Habilitar usuários para Roteamento Direto
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como habilitar os usuários para Microsoft Teams Telefone Roteamento Direto.
ms.openlocfilehash: e82865abcc7bb37835009fb9ab7f93e11c423d66
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774090"
---
# <a name="enable-users-for-direct-routing"></a>Habilitar usuários para Roteamento Direto

Este artigo descreve como habilitar usuários para Roteamento Direto. Esta é a etapa 2 das seguintes etapas para configurar o Roteamento Direto:

- Etapa 1. [Conexão SBC com Sistema de Telefonia validar a conexão](direct-routing-connect-the-sbc.md) 
- **Etapa 2. Habilitar usuários para Roteamento Direto**   (este artigo)
- Etapa 3. [Configurar roteamento de voz](direct-routing-voice-routing.md)
- Etapa 4. [Traduzir números para um formato alternativo](direct-routing-translate-numbers.md) 


Para obter informações sobre todas as etapas necessárias para configurar o Roteamento Direto, consulte [Configure Direct Routing](direct-routing-configure.md).

Quando você estiver pronto para habilitar usuários para Roteamento Direto, siga estas etapas: 

1. Crie um usuário no Microsoft 365 e atribua uma Sistema de Telefonia de usuário.  
2. Verifique se o usuário está em casa online.
3. Configure o número de telefone e habilita a voz corporativa. 
4. Atribua Teams modo Somente aos usuários.

## <a name="create-a-user-and-assign-the-license"></a>Criar um usuário e atribuir a licença

Há duas opções para criar um novo usuário no Microsoft 365. No entanto, a Microsoft recomenda que sua organização escolha uma opção para evitar problemas de roteamento: 

- Crie o usuário no Active Directory local e sincronize o usuário com a nuvem. Consulte [Integrar seus diretórios locais](/azure/active-directory/connect/active-directory-aadconnect) com Azure Active Directory.
- Crie o usuário diretamente no Centro de administração do Microsoft 365. Consulte [Adicionar usuários individualmente ou em massa a Microsoft 365 ou Office 365 - Ajuda do administrador](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Se sua implantação do Skype for Business Online coexistir com o Skype for Business 2015 ou o Lync 2010 ou 2013 local, a única opção com suporte é criar o usuário no Active Directory local e sincronizar o usuário com a nuvem (Opção 1). 

Para obter informações sobre os requisitos de licença, consulte [licenciamento e outros requisitos](direct-routing-plan.md#licensing-and-other-requirements) em [Plan Direct Routing](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-online"></a>Verifique se o usuário está em casa online 

Esta etapa se aplica a Skype for Business Server Enterprise Voice usuários habilitados que estão sendo migrados para Teams Roteamento Direto.

O Roteamento Direto exige que o usuário seja 100% online. Você pode verificar olhando para o parâmetro RegistrarPool, que precisa ter um valor no infra.lync.com domínio. A Microsoft recomenda, mas não exige, que você altere o LineURI de local para online ao migrar usuários para Teams Roteamento Direto. 

1. Conexão uma sessão Microsoft Teams PowerShell.

2. Emitir o comando: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri
    ``` 
    Se OnPremLineUri for preenchido com um número de telefone <E.164>, o número de telefone foi atribuído no local e sincronizado com Microsoft 365. Se você quiser gerenciar o número de telefone online, limpe o parâmetro usando o Shell de Gerenciamento local Skype for Business e sincronia com o Microsoft 365 antes de configurar o número de telefone usando o Teams PowerShell. 

1. A partir Skype for Business Shell de Gerenciamento, emito o comando: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > Não defina EnterpriseVoiceEnabled como False, pois não há requisitos para fazer isso e isso pode levar a problemas de normalização do plano de discagem se os telefones Skype for Business herdados estão em uso e a configuração híbrida tenant é definida com UseOnPremDialPlan $True. 
    
   Depois que as alterações sincronizadas Microsoft 365 a saída esperada `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` de seria:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > Todos os atributos de telefone do usuário devem ser gerenciados online antes de você [decomissioná-lo Skype for Business ambiente local](/skypeforbusiness/hybrid/decommission-on-prem-overview). 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>Configurar o número de telefone e habilitar a voz corporativa 

Depois de criar o usuário e ter atribuído uma licença, você deve configurar as configurações de telefone online do usuário. Observe que a configuração do Caixa postal na Nuvem para o usuário é automática; nenhuma configuração adicional precisa ser feita.

Você pode configurar o número de telefone usando o centro de administração Teams ou usando Teams PowerShell.

### <a name="use-teams-admin-center"></a>Usar Teams de administração

1. Vá para **UsuáriosManage** ->  usuários.

2. Selecione um usuário.

2. Em **Informações Gerais** **da Conta**, selecione **Editar**.

3. Em **Atribuir número de telefone**, Telefone menu suspenso tipo **de** número, selecione **Roteamento Direto**.

4. Insira um número de telefone atribuído e uma extensão de número de telefone, se possível.

5. Selecione **Aplicar.**

As informações gerais da conta agora mostrarão o número de telefone atribuído e o Roteamento Direto como o tipo de número de telefone.


### <a name="use-powershell"></a>Usar o PowerShell

1. Conexão para uma sessão Microsoft Teams PowerShell. 

2. As próximas etapas dependem se você está gerenciando o número de telefone do usuário local ou online. Se você estiver gerenciando o número de telefone local, deverá usar o Shell de Gerenciamento do Skype for Business local, o Painel de Controle ou um dos métodos explicados em Decidir como gerenciar atributos após a [descommisão](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes).

   - Se você estiver gerenciando o número de telefone do usuário no local, você precisará garantir que o usuário Enterprise Voice habilitado online usando o seguinte comando:

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - Se você estiver gerenciando o número de telefone do usuário online, precisará atribuir o número de telefone ao usuário usando o seguinte comando no Teams PowerShell. O usuário é automaticamente Enterprise Voice habilitado pelo comando: 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       Por exemplo, para adicionar um número de telefone para o usuário "Spencer Low", digite o seguinte: 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       Se os usuários "Spencer Low" e "Stacy Quinn" compartilharem o mesmo número base com extensões exclusivas, insira o seguinte
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    A Microsoft recomenda, mas não exige, que o número de telefone seja configurado como um número de telefone E.164 completo com código de país. Você pode configurar números de telefone com extensões. Essas extensões serão usadas para procurar usuários quando a pesquisa em relação ao número base retornar mais de um resultado. Essa funcionalidade permite que as empresas configurem números de telefone com o mesmo número base e extensões exclusivas. Para que a pesquisa seja bem-sucedida, o convite deve incluir o número completo com extensão da seguinte forma:
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>Configurar o envio de chamadas diretamente para a caixa postal

O Roteamento Direto permite que você termine a chamada para um usuário e envie-a diretamente para a caixa postal do usuário. Se você quiser enviar a chamada diretamente para a caixa postal, anexe opaque=app:voicemail ao header request URI. Por exemplo, "sip:user@yourdomain.com;opaque=app:voicemail". O Teams usuário não receberá a notificação de chamada, a chamada será conectada diretamente à caixa postal do usuário.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Atribuir Teams modo Somente aos usuários para garantir que as chamadas land in Microsoft Teams

O Roteamento Direto exige que os usuários Teams modo Somente para garantir que as chamadas de entrada chegam no Teams cliente. Para colocar os usuários Teams modo Somente, atribua a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy. Para obter mais informações, [consulte Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md). Se sua organização usa Skype for Business Server, consulte o artigo a seguir para obter informações sobre interoperabilidade entre Skype e Teams: Migração e [interoperabilidade com Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
