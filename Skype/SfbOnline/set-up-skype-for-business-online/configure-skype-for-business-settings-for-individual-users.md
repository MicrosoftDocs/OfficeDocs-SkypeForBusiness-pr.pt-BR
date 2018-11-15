---
title: Administradores Definir as configurações do Skype for Business para usuários individuais
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
ms.openlocfilehash: e686e42771b22d7c8d8b21ac05998bbbd5f9ad7e
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532547"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administradores: Definir as configurações do Skype for Business para usuários individuais

Este artigo explica como os administradores configuram o Skype for Business para um pequeno número de usuários. Para fazer estas etapas em massa, incluímos links para cmdlets do Windows PowerShell que você pode usar.
  
Para permitir (ou impedir) que todos na empresa se comuniquem com pessoas externas, veja:
  
- [Permitir que os usuários entrar em contato com o Skype externo para usuários comerciais](allow-users-to-contact-external-skype-for-business-users.md): permitem que sua organização use avançadas Skype para recursos corporativos (compartilhamento de desktops, procure por quem está online, etc) para se comunicar com pessoas em uma determinada confiáveis corporativos (federados). O artigo também explica como bloquear a comunicação com domínios específicos.
    
- [Permitir que o Skype para usuários comerciais adicionar contatos do Skype](let-skype-for-business-users-add-skype-contacts.md). Você pode permitir que sua organização use o Skype for Business para procurar usuários do aplicativo gratuito Skype e enviar mensagens instantâneas para eles.
    
## <a name="configure-general-settings-for-one-user"></a>Definir configurações gerais para um usuário
<a name="__toc325019204"> </a>

Você deve ter [permissões de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar estas etapas.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**
  
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
|Áudio e vídeo em HD  <br/> |Permitir que essa pessoa gravem reuniões de áudio, reuniões de áudio e vídeos ou não permiti-los agendar reuniões (nenhum).  <br/> |
|Gravar conversas e reuniões  <br/> |Escolha o que esta pessoa tem permissão para gravar.  <br/> Essa opção não está disponível com Skype para básica de negócios.  <br/> |
|Para fins de conformidade, desligue os recursos não arquivados  <br/> | Selecione esta opção se você for obrigado legalmente a preservar informações armazenadas eletronicamente. <br/>  Esta opção desativa a recursos que não são capturados quando você tem um [Bloqueio In-loco](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configurados no Centro de administração do Exchange. Ele desativa os seguintes recursos: <br/>  Transferência de arquivos usando mensagens de chat <br/>  Páginas do OneNote compartilhadas <br/>  Anotações do PowerPoint <br/> |
   
Para definir essas configurações em massa, use o PowerShell. Consulte [Gerenciando diretivas no Skype para negócios Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## <a name="block-external-communications"></a>Bloquear comunicações externas
<a name="__toc325019206"> </a>

Depois de [Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md) para todos na sua empresa, você pode bloquear seletivamente as comunicações externas de indivíduos específicos usando estas etapas.
  
1. Escolher **usuários**, selecione os usuários cujas configurações você deseja desabilitar e escolha **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Escolha **Comunicações externas** e desmarque as opções conforme apropriado:
    
   - **Usuários externos do Skype for Business**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do Skype for Business em domínios federados.
    
   - **Usuários externos do Skype**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do aplicativo Skype gratuito.
    
3. Clique em **Salvar**.
    
Para definir essas configurações em massa, use o PowerShell. Consulte [Gerenciando communications no Skype para negócios Online com externo usuários e organizações](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Editar configurações de conferência de áudio para um usuário
<a name="__toc314837483"> </a>

1. Escolher **usuários**, selecione o usuário cujas configurações de conferência de áudio que você quer editar, e escolha **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Escolha a **conferência de áudio**, selecione seu provedor de serviços de audioconferência, digite ou alterar as informações solicitadas e clique em **Salvar**.
    
|**Configuração da audioconferência**|**Descrição**|
|:-----|:-----|
|**Nome do provedor** <br/> |Escolha seu provedor da lista.  <br/> |
|**Número de chamada tarifada** (obrigatório) <br/> |Para um ACP de terceiros, esses números de telefone são os que você recebeu do provedor de serviços de audioconferência. Se o usuário estiver usando o Microsoft como um provedor de audioconferência, estes serão os números definidos na ponte de audioconferência. Formate os números de como você deseja que apareçam na Skype para solicitações de reunião de negócios e Teams da Microsoft.  <br/> |
|**Número de chamada gratuita** <br/> |Para um ACP de terceiros, esses números de telefone são os que você recebeu do provedor de serviços de audioconferência. Se o usuário estiver usando o Microsoft como um provedor de audioconferência, estes serão os números definidos na ponte de audioconferência. Formate os números de como você deseja que apareçam na Skype para solicitações de reunião de negócios e Teams da Microsoft.  <br/> |
|**PIN e ID de conferência** (necessário) <br/> |O código PIN do participante ou conferência, usado para ingressar em reuniões que são agendadas pelo usuário e são fornecidos a partir de um provedor de serviços de audioconferência de terceiros. Se o usuário está usando o Microsoft como um provedor de serviços de audioconferência, isso não será necessário.  <br/> |
   
Para definir essas configurações em massa, use o PowerShell. Consulte [Definir convidam números incluídos no telefone](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Tópicos relacionados 

[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)

[Licenciamento de complementos do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 