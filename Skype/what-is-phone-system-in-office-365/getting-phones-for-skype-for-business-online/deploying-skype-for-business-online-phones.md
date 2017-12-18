---
title: "Implantar telefones para o Skype for Business Online"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
description: "Learn the deployment steps to get the correct firmware, update it if needed, assign licences, and configure settings for Skype for Business online phones"
---

# Implantar telefones para o Skype for Business Online

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Este guia de implantação ajudará você a implantar os telefones IP do Skype for Business Online.
  
In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Obter telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
## Etapas da implantação para telefones IP

### Etapa 1 - Baixe os guias de administrador do fabricante e manuais do telefone

Antes de iniciar, é recomendável baixar os guias de administração do fabricante e dos manuais do usuário do telefone.
  
- Para os telefones Polycom, consulte o [Guia de Implantação Polycom](https://support.polycom.com/PolycomService/support/us/support/voice/polycom_uc/polycom_uc_software_for_lync.mdl).
    
- For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/solution_7.mdl).
    
- Para telefones AudioCodes, consulte o [Guia de Gerenciamento de Provisionamento Audiocodes ](https://www.audiocodes.com/products/ems).
    
### Etapa 2 - Certifique-se de que você está migrando para um telefone IP e firmware compatíveis com o Skype for Business ou adquirindo um assim.

A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Obter telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
### Etapa 3 - Verificar se o firmware certo foi instalado e atualizar o firmware, se necessário

Check the firmware version on your phones. For:
  
- **Telefones Polycom VVX**, vá para **Configurações** > **Status** > **Plataforma** > **Aplicativo** > **Principal**.
    
- **Telefones Yealink**, vá para **Status** na tela do telefone principal.
    
- **Telefones AudioCodes**, vá para **Menu** > ** Status do Dispositivo** > **Versão do Firmware** na tela inicial.
    
    > [!NOTE]
    > For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals. 
  
- **Telefones Lync Phone Edition (LPE)**, vá para **Menu** > **Informações do Sistema** na tela inicial.
    
### Etapa 4 - Considerações sobre atualização do dispositivo

> [!NOTE]
> Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1). 
  
Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Para um telefone Polycom, você pode atualizar o firmware no telefone selecionando **SwUpdate**.
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Você também pode optar por gerenciar as atualizações de firmware usando um sistema de provisionamento de parceiros. Para o gerenciamento do sistema de provisionamento de parceiros incluindo a personalização avançada do telefone, consulte os guias de administração do fabricante.
  
> [!CAUTION]
> Certifique-se de ter uma única autoridade de atualização de dispositivo (atualização de dispositivo em banda ou um servidor de provisionamento de terceiro) para evitar loops de atualização. 
  
### Step 5 - Configuration and infrastructure phone settings

Você pode configurar as opções e as políticas do telefone usadas com mais frequência usando os cmdlets do Windows PowerShell de gerenciamento em banda do Skype for Business. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obter detalhes sobre esses parâmetros e configurações.
  
For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### Step 6 - Preparing for users to sign in

To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype para Business e Teams Microsoft complemento licenciamento](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and[Atribuir Skype para Business e Teams Microsoft licenças](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
You can find out more about Calling Plans by reading [O que são chamando planos no Office 365?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
  
- As **opções de logon** que estão disponíveis para os usuários online são:
    
  - Users with **Polycom VVX 5XX/6XX** phones will see:
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Users with **Yealink T48G/T46G** phones will see:
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    For details on sign-in options supported by the manufacturer, see [Obter telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online.md).
    
- **ID do usuário** Usando o teclado do telefone ou o teclado na tela (se disponível), os usuários podem usar o nome e a senha do usuário de sua organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como *amosm@contoso.com*  para seu nome de usuário.
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > A autenticação de PIN não é aceita no Skype for Business Online para telefones LPE e telefones IP de parceiros. 
  
- **Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See[Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivo e Better Together over Ethernet (BToE)](faa17eb3-7483-4984-87f2-815d981b68ae.md#BK_BTOE) for other information.
    
    > [!NOTE]
    > Os usuários devem usar o nome de usuário e senha da organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como  *amosm@contoso.com*  para seu nome de usuário.
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.
    
  - Users with **Polycom VVX 5XX/6XX** phones will see:
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Users with **Yealink T48G/T46G** phones will see:
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.
    
  - Users with **Polycom VVX 5XX/6XX** phones will see:
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Users with **Yealink T48G/T46G** phones will see:
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Usando um navegador, navegue até o endereço exibido no telefone e digite o nome do usuário do Skype for Business.
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Digite o código mostrado no telefone.
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Clique nas credenciais do usuário ou clique em **Usar outra conta**:
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    When the following page is displayed, it is safe to close the browser.
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > Os telefones LPE para Skype for Business Online permitem logon somente por meio de compartilhamento USB. 
  
- **Implantações suportadas** A tabela abaixo mostra os tipos de autenticação permitidos para os modelos de implantação aceitos atualmente incluindo a Integração com o Exchange, Autenticação moderna com o MFA (Multi-factor Authentication, Autenticação Multifator) e o Skype for Business Online e locais.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**Exchange** <br/> |**Método de entrada de telefone** <br/> |**Skype for Business access** <br/> |**Acesso do Exchange com Autenticação Multifator e MFA desabilitados** <br/> |**Acesso do Exchange com Autenticação Multifator e MFA habilitados** <br/> |
|Online  <br/> |Online  <br/> |Entrada da Web  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Online  <br/> |Online  <br/> |Nome do usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Online  <br/> |Locais  <br/> |Entrada da Web  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Online  <br/> |Locais  <br/> |Nome do usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Locais  <br/> |Online/Locais  <br/> |Autenticação por PIN  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Locais  <br/> |Online/Locais  <br/> |Nome do usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |N/A  <br/> |
|Locais  <br/> |Online/Locais  <br/> |Entrada via PC (BTOE)  <br/> |Sim  <br/> |Sim  <br/> |N/D  <br/> |
   
- **Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see[Obter telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online.md).
    
- **Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.
    
    You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.
    
## Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivo e Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:
  
- Sign in to their IP phone using their Skype for Business desktop app (using a PC)
    
- Synchronize Phone-Lock with PC lock
    
- Click to call
    
BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.
  
 **To deploy BToE to users**
  
1. Conecte o PC deles ao telefone usando a porta do PC.
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Baixe e instale o software BToE mais recente do site do fabricante usando os links abaixo. Para uma melhor experiência do usuário, você pode distribuir e instalar o software BToE usando uma solução de distribuição de administração como o SCCM (System Center Configuration Manager). Para obter ajudar sobre como usar o SCCM, consulte [Pacotes e programas no System Center Configuration Manager](https://docs.microsoft.com/pt-br/sccm/apps/deploy-use/packages-and-programs).
    
  - [Polycom BToE Software Download site](https://support.polycom.com/PolycomService/support/us/support/voice/polycom_uc/polycom_uc_software_for_lync.mdl)
    
  - [Download de software BToE Yealink](http://www.yealink.com/solution_info.aspx?ProductsCateID=1471&amp;parentcateid=1471&amp;cateid=1471&amp;BaseInfoCateId=1328&amp;Cate_Id=1471)
    
  - [Downloads de software BToE AudioCodes](ftp://VoP-C12:IPPLync@ftp.audiocodes.com/Release/3.0.0.Beta/BToE_1.1.8/)
    
3. The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see[Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> O BToE não é permitido atualmente nas plataformas Mac e VDI. 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

