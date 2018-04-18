---
title: Administradores Definir as configurações do Skype for Business para usuários individuais
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 930960117a46639e86ed2d24c286a5270b21acb9
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administradores: Definir as configurações do Skype for Business para usuários individuais

Este artigo explica como os administradores configuram o Skype for Business para um pequeno número de usuários. To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.
  
Para permitir (ou impedir) que todos na empresa se comuniquem com pessoas externas, veja:
  
- [Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business. The article also explains how to block communication with specific domains.
    
- [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md). Você pode permitir que sua organização use o Skype for Business para procurar usuários do aplicativo gratuito Skype e enviar mensagens instantâneas para eles.
    
## <a name="configure-general-settings-for-one-user"></a>Definir configurações gerais para um usuário
<a name="__toc325019204"> </a>

You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Escolha **Centros de administração** > **Skype for Business**.
    
3. Escolha **Usuários**.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Selecione quais usuários você deseja editar:
    
5. No painel direito, escolha **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Na página de opções **Geral**, marque ou desmarque a caixa de seleção ao lado dos recursos que você quer alterar e clique em **Salvar**.
    
|**Opção**|**Detalhes**|
|:-----|:-----|
|Áudio e vídeo em HD  <br/> |Permita que esta pessoa grave reuniões de áudio, reuniões de áudio e vídeo e áudio, ou não permita que agendem nenhuma reunião (nenhum).  <br/> |
|Gravar conversas e reuniões  <br/> |Escolha o que esta pessoa tem permissão para gravar.  <br/> This option is not available with Skype for Business Basic.  <br/> |
|Para fins de conformidade, desligue os recursos não arquivados  <br/> | Selecione esta opção se você for obrigado legalmente a preservar informações armazenadas eletronicamente. <br/>  Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center. Ele desativa os seguintes recursos: <br/>  Transferência de arquivos usando mensagens de chat <br/>  Páginas do OneNote compartilhadas <br/>  Anotações do PowerPoint <br/> |
   
To configure these settings in bulk, use PowerShell. See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## <a name="block-external-communications"></a>Bloquear comunicações externas
<a name="__toc325019206"> </a>

Depois de [Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md) para todos na sua empresa, você pode bloquear seletivamente as comunicações externas de indivíduos específicos usando estas etapas.
  
1. Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Escolha **Comunicações externas** e desmarque as opções conforme apropriado:
    
  - **Usuários externos do Skype for Business**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do Skype for Business em domínios federados.
    
  - **Usuários externos do Skype**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do aplicativo Skype gratuito.
    
3. Clique em **Salvar**.
    
To configure these settings in bulk, use PowerShell. See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Edit audio conferencing settings for one user
<a name="__toc314837483"> </a>

1. Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.
    
|**Configuração da audioconferência**|**Descrição**|
|:-----|:-----|
|**Provider name** <br/> |Choose your provider from the list.  <br/> |
|**Número de chamada tarifada** (obrigatório) <br/> |For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Número de chamada gratuita** <br/> |For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Conference ID and PIN** (required) <br/> |The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, this won't be required.  <br/> |
   
To configure these settings in bulk, use PowerShell. See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Tópicos relacionados 

[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)

[Licenciamento de complementos do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 