---
title: Administradores Definir as configurações do Skype for Business para usuários individuais
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: d6054db4bfdd8b161dca427237a10d70ba558fcb
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769684"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administradores: Definir as configurações do Skype for Business para usuários individuais

Este artigo explica como os administradores configuram o Skype for Business para um pequeno número de usuários. Para executar essas etapas em massa, incluímos links para os cmdlets do Windows PowerShell que você pode usar.
  
Para permitir (ou impedir) que todos na empresa se comuniquem com pessoas externas, veja:
  
- [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](allow-users-to-contact-external-skype-for-business-users.md): você pode permitir que sua organização use recursos avançados do Skype for Business (Compartilhe áreas de trabalho, procure quem está online etc.) para se comunicar com as pessoas de uma empresa confiável (federada) específica. O artigo também explica como bloquear a comunicação com domínios específicos.
    
- [Deixe que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md). Você pode permitir que sua organização use o Skype for Business para procurar usuários do aplicativo gratuito Skype e enviar mensagens instantâneas para eles.
    
## <a name="configure-general-settings-for-one-user"></a>Definir configurações gerais para um usuário
<a name="__toc325019204"> </a>

Você deve ter [permissões de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar essas etapas.

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**
  
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
|Áudio e vídeo em HD  <br/> |Permita que esta pessoa grave reuniões de áudio, reuniões de áudio e vídeo ou não permita que elas agendem reuniões (nenhuma).  <br/> |
|Gravar conversas e reuniões  <br/> |Escolha o que esta pessoa tem permissão para gravar.  <br/> Essa opção não está disponível com o Skype for Business Basic.  <br/> |
|Para fins de conformidade, desligue os recursos não arquivados  <br/> | Selecione esta opção se você for obrigado legalmente a preservar informações armazenadas eletronicamente. <br/>  Selecionar essa opção desativa os recursos que não são capturados quando você tem um [bloqueio in-loco](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configurado no centro de administração do Exchange. Ele desativa os seguintes recursos: <br/>  Transferência de arquivos usando mensagens de chat <br/>  Páginas do OneNote compartilhadas <br/>  Anotações do PowerPoint <br/> |
   
Para definir essas configurações em massa, use o PowerShell. Consulte [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="block-external-communications"></a>Bloquear comunicações externas
<a name="__toc325019206"> </a>

Depois de [Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md) para todos na sua empresa, você pode bloquear seletivamente as comunicações externas de indivíduos específicos usando estas etapas.
  
1. Escolha **usuários**, selecione os usuários cujas configurações você deseja desabilitar e escolha **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Escolha **Comunicações externas** e desmarque as opções conforme apropriado:
    
   - **Usuários externos do Skype for Business**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do Skype for Business em domínios federados.
    
   - **Usuários externos do Skype**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do aplicativo Skype gratuito.
    
3. Clique em **Salvar**.
    
Para definir essas configurações em massa, use o PowerShell. Consulte [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Editar as configurações de audioconferência de áudio para um usuário
<a name="__toc314837483"> </a>

1. Escolha **usuários**, selecione o usuário cujas configurações de audioconferência você deseja editar e escolha **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Escolha **videoconferência**, selecione seu provedor de serviços de audioconferência, digite ou altere as informações solicitadas e clique em **salvar**.
    
|**Configuração da audioconferência**|**Descrição**|
|:-----|:-----|
|**Nome do provedor** <br/> |Escolha seu provedor na lista.  <br/> |
|**Número de chamada tarifada** (obrigatório) <br/> |Para um ACP terceirizado, esses números de telefone são aqueles que você recebeu do provedor de serviços de audioconferência. Se o usuário estiver usando o Microsoft como um provedor de audioconferência, estes serão os números definidos na ponte de audioconferência. Formate os números como deseja que eles apareçam nas solicitações de reunião do Skype for Business e do Microsoft Teams.  <br/> |
|**Número de chamada gratuita** <br/> |Para um ACP terceirizado, esses números de telefone são aqueles que você recebeu do provedor de serviços de audioconferência. Se o usuário estiver usando o Microsoft como um provedor de audioconferência, estes serão os números definidos na ponte de audioconferência. Formate os números como deseja que eles apareçam nas solicitações de reunião do Skype for Business e do Microsoft Teams.  <br/> |
|**ID de conferência e PIN** (obrigatório) <br/> |O PIN do participante ou o código de conferência usado para ingressar em reuniões agendadas por esse usuário e são fornecidas por um provedor de serviços de audioconferência de terceiros. Se o usuário estiver usando a Microsoft como provedor de serviços de audioconferência, isso não será necessário.  <br/> |
   
Para definir essas configurações em massa, use o PowerShell. Consulte [definir os números de telefone incluídos nos convites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Tópicos relacionados 

[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)

[Licenciamento de complementos do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
