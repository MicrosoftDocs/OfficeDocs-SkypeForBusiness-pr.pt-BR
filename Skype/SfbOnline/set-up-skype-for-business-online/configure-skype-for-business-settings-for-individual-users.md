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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: e96e33f5a83030f187c6e6c3caaee197c2d81a2f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731820"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Administradores: Definir as configurações do Skype for Business para usuários individuais

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> O Microsoft Teams de administração substituiu o Skype for Business de administração (portal herdado). Todas as configurações para o Skype for Business agora estão no centro Teams administrador. Você deve ter a função de administrador do [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global ou Skype for Business para gerenciar Skype for Business recursos no centro de administração Teams do Azure. Para obter mais informações, confira [Gerenciar as configurações do Skype for Business do centro de Administração do Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).

Este artigo explica como os administradores configuram o Skype for Business para um pequeno número de usuários. Para fazer essas etapas em massa, incluímos links para os cmdlets Windows PowerShell que você pode usar.
  
Para permitir (ou impedir) que todos na empresa se comuniquem com pessoas externas, veja:
  
- Permitir que os usuários contatem usuários externos [Skype for Business](allow-users-to-contact-external-skype-for-business-users.md): Você pode permitir que sua organização use recursos avançados de Skype for Business (compartilhar áreas de trabalho, procurar quem está online, etc.) para se comunicar com pessoas em uma empresa confiável (federada) específica. O artigo também explica como bloquear a comunicação com domínios específicos.
    
- [Permitir Skype for Business usuários adicionem Skype contatos](let-skype-for-business-users-add-skype-contacts.md). Você pode permitir que sua organização use o Skype for Business para procurar usuários do aplicativo gratuito Skype e enviar mensagens instantâneas para eles.
    
## <a name="configure-general-settings-for-one-user"></a>Definir configurações gerais para um usuário
<a name="__toc325019204"> </a>

Você deve ter [permissões de administrador](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar essas etapas.

![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png) **Usando o Skype for Business de administração**
  
1. Entre com sua conta de trabalho ou de estudante.
    
2. Escolha **Centros de administração** > **Skype for Business**.
    
3. Escolha **Usuários**.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Selecione quais usuários você deseja editar:
    
5. No painel direito, escolha **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Na página de opções **Geral**, marque ou desmarque a caixa de seleção ao lado dos recursos que você quer alterar e clique em **Salvar**.
    
|**Opção**|**Detalhes**|
|:-----|:-----|
|Áudio e vídeo em HD  <br/> |Permitir que essa pessoa grave reuniões de áudio, áudio e vídeo ou não permita que ela agende reuniões (nenhuma).  <br/> |
|Gravar conversas e reuniões  <br/> |Escolha o que esta pessoa tem permissão para gravar.  <br/> Essa opção não está disponível com o Skype for Business Basic.  <br/> |
|Para fins de conformidade, desligue os recursos não arquivados  <br/> | Selecione esta opção se você for obrigado legalmente a preservar informações armazenadas eletronicamente. <br/>  Selecionar essa opção desabilita os recursos que não são capturados quando você tem um Hold [in-locar](/exchange/security-and-compliance/in-place-and-litigation-holds) definido no centro de administração Exchange local. Ele desativa os seguintes recursos: <br/>  Transferência de arquivos usando mensagens de chat <br/>  Páginas do OneNote compartilhadas <br/>  Anotações do PowerPoint <br/> |
   
Para configurar essas configurações em massa, use o PowerShell. Consulte [Configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="block-external-communications"></a>Bloquear comunicações externas
<a name="__toc325019206"> </a>

Depois de [Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md) para todos na sua empresa, você pode bloquear seletivamente as comunicações externas de indivíduos específicos usando estas etapas.
  
1. Escolha **Usuários**, selecione os usuários cujas configurações você deseja desabilitar e escolha **Editar** ![ Editar. ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .
    
2. Escolha **Comunicações externas** e desmarque as opções conforme apropriado:
    
   - **Usuários externos do Skype for Business**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do Skype for Business em domínios federados.
    
   - **Usuários externos do Skype**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do aplicativo Skype gratuito.
    
3. Clique em **Salvar**.
    
Para configurar essas configurações em massa, use o PowerShell. Consulte [Configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Editar configurações de audioconferência para um usuário
<a name="__toc314837483"> </a>

1. Escolha **Usuários**, selecione o usuário cujas configurações de audioconferência você quer editar e, em seguida, escolha **Editar** ![ Editar. ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .
    
2. Escolha **Audioconferência**, selecione seu provedor de audioconferência, digite ou altere as informações solicitadas e clique em **Salvar**.
    
|**Configuração da audioconferência**|**Descrição**|
|:-----|:-----|
|**Nome do provedor** <br/> |Escolha seu provedor na lista.  <br/> |
|**Número de chamada tarifada** (obrigatório) <br/> |Para um ACP de terceiros, esses números de telefone são os que você recebeu do provedor de audioconferência. Se o usuário estiver usando o Microsoft como um provedor de audioconferência, estes serão os números definidos na ponte de audioconferência. Formatar os números conforme você deseja que eles apareçam em Skype for Business e Microsoft Teams de reunião.  <br/> |
|**Número de chamada gratuita** <br/> |Para um ACP de terceiros, esses números de telefone são os que você recebeu do provedor de audioconferência. Se o usuário estiver usando o Microsoft como um provedor de audioconferência, estes serão os números definidos na ponte de audioconferência. Formatar os números conforme você deseja que eles apareçam em Skype for Business e Microsoft Teams de reunião.  <br/> |
|**ID de conferência e PIN** (obrigatório) <br/> |O PIN participante, ou código de conferência, usado para ingressar em reuniões agendadas por esse usuário e são fornecidos de um provedor de audioconferência de terceiros. Se o usuário estiver usando a Microsoft como provedor de audioconferência, isso não será necessário.  <br/> |
   
Para configurar essas configurações em massa, use o PowerShell. Consulte [Definir os números de telefone incluídos em convites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) Configurar seu computador [para](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell .


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Tópicos relacionados 

[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)

[Licenciamento de complementos do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
