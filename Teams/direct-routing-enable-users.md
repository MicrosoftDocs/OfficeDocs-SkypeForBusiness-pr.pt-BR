---
title: Habilitar usuários para Roteamento Direto
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
description: Saiba como habilitar os usuários Telefone Microsoft Roteamento Direto do Sistema.
ms.openlocfilehash: e15e73c74b6597f754287077480316a8da98178985ef49603cf0fb3b8dc02bbe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327676"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Habilitar usuários para Roteamento Direto, voz e caixa postal

Este artigo descreve como habilitar os usuários para Sistema de Telefonia Roteamento Direto.  Esta é a etapa 2 das seguintes etapas para configurar o Roteamento Direto:

- Etapa 1. [Conexão SBC com Telefone Microsoft System e validar a conexão](direct-routing-connect-the-sbc.md) 
- **Etapa 2. Habilitar usuários para Roteamento Direto, voz e caixa postal**   (este artigo)
- Etapa 3. [Configurar roteamento de voz](direct-routing-voice-routing.md)
- Etapa 4. [Traduzir números para um formato alternativo](direct-routing-translate-numbers.md) 


Para obter informações sobre todas as etapas necessárias para configurar o Roteamento Direto, consulte [Configure Direct Routing](direct-routing-configure.md).

Quando você estiver pronto para habilitar usuários para Roteamento Direto, siga estas etapas: 

1. Crie um usuário no Microsoft 365 ou Office 365 e atribua uma Sistema de Telefonia de usuário. 
2. Verifique se o usuário está no Skype for Business Online. 
3. Configure o número de telefone e habilita a voz corporativa e a caixa postal. 
4. Atribua Teams modo Somente aos usuários.

## <a name="create-a-user-and-assign-the-license"></a>Criar um usuário e atribuir a licença

Há duas opções para criar um novo usuário no Microsoft 365 ou Office 365. No entanto, a Microsoft recomenda que sua organização escolha uma opção para evitar problemas de roteamento: 

- Crie o usuário no Active Directory local e sincronize o usuário com a nuvem. Consulte [Integrar seus diretórios locais com Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).
- Crie o usuário diretamente no Centro de administração do Microsoft 365. Consulte [Adicionar usuários individualmente ou em massa a](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)Microsoft 365 ou Office 365 - Ajuda do administrador . 

Se sua implantação do Skype for Business Online coexistir com o Skype for Business 2015 ou o Lync 2010 ou 2013 local, a única opção com suporte é criar o usuário no Active Directory local e sincronizar o usuário com a nuvem (Opção 1). 

Para obter informações sobre os requisitos de licença, consulte [licenciamento e outros requisitos](direct-routing-plan.md#licensing-and-other-requirements) em [Plan Direct Routing](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-online"></a>Verifique se o usuário está em casa online 

Esta etapa é aplicável Skype for Business Server Enterprise Voice usuários habilitados que estão sendo migrados para Teams Roteamento Direto.

O Roteamento Direto exige que o usuário seja 100% online. Você pode verificar olhando para o parâmetro RegistrarPool, que precisa ter um valor no infra.lync.com domínio. Também é recomendável, mas não necessário, alterar o gerenciamento do LineURI de local para online ao migrar usuários para Teams Roteamento Direto. 

1. Conexão uma sessão Skype for Business Do PowerShell Online.

2. Emitir o comando: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Caso OnPremLineUriManuallySet seja definido como False e LineUri for preenchido com um número de telefone do <E.164>, o número de telefone foi atribuído no local e sincronizado com o O365. Se você quiser gerenciar o número de telefone online, limpe o parâmetro usando o Shell de Gerenciamento local Skype for Business e sincronizar com o O365, antes de configurar o número de telefone usando o Skype for Business Online PowerShell. 

1. A partir Skype for Business Shell de Gerenciamento em questão o comando: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > Não defina EnterpriseVoiceEnabled como False, pois não há nenhum requisito para fazer isso e isso pode levar a problemas de normalização do plano de discagem se os telefones Skype for Business herdados estão em uso e a configuração híbrida tenant é definida com UseOnPremDialPlan $True. 
    
   Depois que as alterações sincronizadas Office 365 a saída esperada `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` de seria:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > Todos os atributos de telefone do usuário devem ser gerenciados online antes de você [decomissioná-lo Skype for Business ambiente local.](/skypeforbusiness/hybrid/decommission-on-prem-overview) 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online"></a>Configurar o número de telefone e habilitar a voz corporativa e a caixa postal online 

Depois de ter criado o usuário e atribuído uma licença, a próxima etapa é configurar as configurações de telefone online do usuário. 

 
1. Conexão uma sessão Skype for Business Do PowerShell Online. 

2. Se o gerenciamento do número de telefone do usuário no local, emito o comando: 

    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
3. Se o gerenciamento do número de telefone do usuário online, emito o comando: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    Por exemplo, para adicionar um número de telefone para o usuário "Spencer Low", digite o seguinte: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    Se os usuários "Spencer Low" e "Stacy Quinn" compartilharem o mesmo número base com extensões exclusivas, insira o seguinte
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    É recomendável, mas não obrigatório, que o número de telefone usado seja configurado como um número de telefone E.164 completo com código de país. Há suporte para configurar números de telefone com extensões que serão usadas para procurar usuários quando a pesquisa em relação ao número base retornar mais de um resultado. Isso permite que as empresas configurem números de telefone com o mesmo número base e extensões exclusivas. Para que a pesquisa seja bem-sucedida, o convite deve incluir o número completo com extensão da seguinte forma:
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > Se o número de telefone do usuário for gerenciado no local, use o Shell de Gerenciamento local Skype for Business Shell de Gerenciamento ou Painel de Controle para configurar o número de telefone do usuário. 


## <a name="configure-sending-calls-directly-to-voicemail"></a>Configurar o envio de chamadas diretamente para a caixa postal

O Roteamento Direto permite que você termine a chamada para um usuário e envie-a diretamente para a caixa postal do usuário. Se você quiser enviar a chamada diretamente para a caixa postal, anexe opaque=app:voicemail ao header request URI. Por exemplo, "sip:user@yourdomain.com;opaque=app:voicemail". Nesse caso, o Teams usuário não receberá a notificação de chamada, a chamada será conectada diretamente à caixa postal do usuário.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Atribuir Teams modo Somente aos usuários para garantir que as chamadas aterrisem Microsoft Teams

O Roteamento Direto exige que os usuários Teams modo Somente para garantir que as chamadas de entrada chegam no Teams cliente. Para colocar os usuários Teams modo Somente, atribua a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy. Para obter mais informações, [consulte Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md). Se sua organização usa Skype for Business Server ou Skype for Business Online, consulte o artigo a seguir para obter informações sobre interoperabilidade entre Skype e Teams: Migração e [interoperabilidade](migration-interop-guidance-for-teams-with-skype.md)com Skype for Business .

## <a name="see-also"></a>Confira também

[Planejar o Roteamento Direto](direct-routing-plan.md)

[Configurar o Roteamento Direto](direct-routing-configure.md)
