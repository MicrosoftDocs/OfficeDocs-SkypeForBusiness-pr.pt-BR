---
title: Implantar telefones para o Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Conheça as etapas de implantação para obter o firmware correto, atualizá-la, se necessário, atribuir licenças e definir configurações para Skype para telefones online de negócios
ms.openlocfilehash: 26748f79d62b2f4b40a249dcf1af1736bae2d06f
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374568"
---
# <a name="deploying-skype-for-business-online-phones"></a>Implantar telefones para o Skype for Business Online

Este guia de implantação ajudará você a implantar os telefones IP do Skype for Business Online.
  
In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
## <a name="deployment-steps-for-ip-phones"></a>Etapas da implantação para telefones IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Etapa 1 - Baixe os guias de administrador do fabricante e manuais do telefone

Antes de iniciar, é recomendável baixar os guias de administração do fabricante e dos manuais do usuário do telefone.
  
- Para telefones Polycom, consulte o [Polycom Deployment Guide] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
    
- Para telefones Yealink, consulte [Yealink Skype para a solução de telefones SIP do negócios HD](http://www.yealink.com/products_top_2.html).
    
- Para telefones AudioCodes, consulte o [Guia de Gerenciamento de Provisionamento Audiocodes ](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Etapa 2 - Certifique-se de que você está migrando para um telefone IP e firmware compatíveis com o Skype for Business ou adquirindo um assim.

A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Etapa 3 - Verificar se o firmware certo foi instalado e atualizar o firmware, se necessário

Check the firmware version on your phones. For:
  
- **Telefones Polycom VVX**, vá para **Configurações** > **Status** > **Plataforma** > **Aplicativo** > **Principal**.
    
- **Telefones Yealink**, vá para **Status** na tela do telefone principal.
    
- **Telefones AudioCodes**, acesse **Menu** > **Status do Dispositivo** > **Versão do firmware** na tela inicial.
    
    > [!NOTE]
    > For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals. 
  
- **Telefones Lync Phone Edition (LPE)**, vá para **Menu** > **Informações do Sistema** na tela inicial.
    
### <a name="step-4---device-update-considerations"></a>Etapa 4 - Considerações sobre atualização do dispositivo

> [!NOTE]
> Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1). 
  
Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.
  
![Implementar telefones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.
  
![Implementar telefones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Para um telefone Polycom, você pode atualizar o firmware no telefone selecionando **SwUpdate**.
  
![Implementar telefones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Você também pode optar por gerenciar as atualizações de firmware usando um sistema de provisionamento de parceiros. Para o gerenciamento do sistema de provisionamento de parceiros incluindo a personalização avançada do telefone, consulte os guias de administração do fabricante.
  
> [!CAUTION]
> [!CUIDADO] Certifique-se de ter uma única autoridade de atualização de dispositivo (atualização de dispositivo em banda ou um servidor de provisionamento de terceiro) para evitar loops de atualização. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Etapa 5 - configuração e definições de telefone de infra-estrutura

Você pode configurar as opções e as políticas do telefone usadas com mais frequência usando os cmdlets do Windows PowerShell de gerenciamento em banda do Skype for Business. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obter detalhes sobre esses parâmetros e configurações.
  
Para o planejamento da infra-estrutura de rede, consulte [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Etapa 6 - Preparando os usuários entrem em

To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Você pode encontrar mais informações sobre Planos de Chamadas em [O que são os Planos de Chamadas do Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)
  
- As **opções de logon** que estão disponíveis para os usuários online são:
    
  - Usuários com telefones **Polycom VVX 5XX/6XX** verá:
    
     ![Implementar telefones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Usuários com telefones **Yealink T48G/T46G** verá:
    
     ![Logon de telefones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Para obter detalhes sobre as opções de entrar suportadas pelo fabricante, consulte [Getting telefones para Skype para negócios Online](getting-phones-for-skype-for-business-online.md).
    
- **ID do usuário** Usando o teclado do telefone ou o teclado na tela (se disponível), os usuários podem usar o nome e a senha do usuário de sua organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como <em>amosm@contoso.com</em>  para seu nome de usuário.
    
     ![Implementar telefones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > [!OBSERVAçãO] A autenticação de PIN não é aceita no Skype for Business Online para telefones LPE e telefones IP de parceiros. 
  
- **Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.
    
  > [!NOTE]
  > [!OBSERVAçãO] Os usuários devem usar o nome de usuário e senha da organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como  <em>amosm@contoso.com</em>  para seu nome de usuário.
  
     ![Implementar telefones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.
    
  - Usuários com telefones **Polycom VVX 5XX/6XX** verá:
    
     ![Implementar telefones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Usuários com telefones **Yealink T48G/T46G** verá:
    
     ![Logon de telefone Yealink.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.
    
  - Usuários com telefones **Polycom VVX 5XX/6XX** verá:
    
     ![Código PIN expirado.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Usuários com telefones **Yealink T48G/T46G** verá:
    
     ![Logon de telefones Yealink.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Usando um navegador, navegue até o endereço exibido no telefone e digite o nome do usuário do Skype for Business.
    
     ![Implementar telefones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Digite o código mostrado no telefone.
    
     ![Implementar telefones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Verifique se o site mostra "[nome do fabricante do telefone] **Skype para negócios Certified Phone**," e clique em **continuar**.
    
     ![Implementar telefones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Clique nas credenciais do usuário ou clique em **Usar outra conta**:
    
     ![Implementar telefones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Quando for exibida a página seguinte, é seguro fechar o navegador.
    
     ![Implementar telefones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > [!OBSERVAçãO] Os telefones LPE para Skype for Business Online permitem logon somente por meio de compartilhamento USB. 
  
- **Implantações suportadas** A tabela abaixo mostra os tipos de autenticação permitidos para os modelos de implantação aceitos atualmente incluindo a Integração com o Exchange, Autenticação moderna com o MFA (Multi-factor Authentication, Autenticação Multifator) e o Skype for Business Online e locais.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**Exchange** <br/> |**Método de entrada de telefone** <br/> |**Skype para acesso de negócios** <br/> |**Acesso do Exchange com Autenticação Multifator e MFA desabilitados** <br/> |**Acesso do Exchange com Autenticação Multifator e MFA habilitados** <br/> |
|Online  <br/> |Online  <br/> |Entrada da Web  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Online  <br/> |Online  <br/> |Nome do usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Online  <br/> |Locais  <br/> |Entrada da Web  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Online  <br/> |Locais  <br/> |Nome do usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Locais  <br/> |Online/Locais  <br/> |Autenticação de PIN  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Locais  <br/> |Online/Locais  <br/> |Nome do usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |N/D  <br/> |
|Locais  <br/> |Online/Locais  <br/> |Entrada via PC (BTOE)  <br/> |Sim  <br/> |Sim  <br/> |N/D  <br/> |
   
- **Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
    
- **Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.
    
    You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivo e Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:
  
- Entrar no seu telefone IP usando seu Skype para aplicativos da área de trabalho de negócios (usando um PC)
    
- Sincronizar o bloqueio de telefone com o bloqueio de PC
    
- Clique para chamar
    
BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.
  
 **Implantar BToE para os usuários**
  
1. Conecte o PC deles ao telefone usando a porta do PC.
    
     ![Implementar telefones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Baixe e instale o software BToE mais recente do site do fabricante usando os links abaixo. Para uma melhor experiência do usuário, você pode distribuir e instalar o software BToE usando uma solução de distribuição de administração como o SCCM (System Center Configuration Manager). Para obter ajudar sobre como usar o SCCM, consulte [Pacotes e programas no System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).
    
   - [Site de Download de Software do Polycom BToE](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Download de software BToE Yealink](http://www.yealink.com/products_list_10.html)
    
   - [Downloads de software BToE AudioCodes](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> [!OBSERVAçãO] O BToE não é permitido atualmente nas plataformas Mac e VDI. 
  
## <a name="related-topics"></a>Tópicos relacionados
[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
