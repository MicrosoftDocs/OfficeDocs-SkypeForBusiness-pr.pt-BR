---
title: Gerenciar Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Resumo: saiba como gerenciar o servidor de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 17b9770d2cc3385eb797a1e868c7623f3f09a3ba
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279274"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Gerenciar Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar o servidor de chat persistente no Skype for Business Server 2015.
  
Ao configurar o servidor de chat persistente para a sua organização, você especifica a configuração inicial durante a implantação. No entanto, pode haver ocasiões em que você queira alterar a maneira de implementar o suporte persistente do chat Server. Por exemplo, talvez seja necessário configurar o suporte e os controles persistentes do servidor de chat de forma diferente para uma equipe específica ou um grupo dentro de sua organização. Esta seção fornece informações e procedimentos para ajudá-lo a personalizar a implantação do servidor de chat persistente. Para obter detalhes sobre os recursos e funcionalidades que você pode configurar para o servidor de chat persistente, consulte [plano para servidor de chat persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Para obter detalhes sobre a implantação do servidor de chat persistente, consulte [implantar servidor de chat persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [jornada do Skype for Business para o Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 
  
Você pode gerenciar o servidor de chat persistente usando o painel de controle ou usando cmdlets do Windows PowerShell. 
  
Para usar o Painel de Controle:
  
1. A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.
    
2. No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.
    
3. Na barra de navegação à esquerda, clique em **chat persistente**.
    
A tabela a seguir resume os cmdlets do Windows PowerShell disponíveis para ajudar você a gerenciar o servidor de chat persistente. Para detalhes sobre sintaxe, incluindo todos os parâmetros disponíveis, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Criar uma nova categoria  <br/> |
|Set-CsPersistentChatCategory  <br/> |Definir configurações para uma categoria existente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recupera informações sobre categorias  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Remove uma categoria  <br/> |
|New-CsPersistentChatRoom  <br/> |Cria uma nova sala de chat  <br/> |
|Set-CsPersistentChatRoom  <br/> |Define configurações para uma sala existente; atribui usuários e grupos de usuários à sala  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recupera informações sobre salas  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Limpar uma sala ou as mensagens de uma sala  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Remove uma sala  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Remove as mensagens de uma sala  <br/> |
|New-CsPersistentChatAddin  <br/> |Cria um novo suplemento  <br/> |
|Set-CsPersistentChatAddin  <br/> |Define configurações para um suplemento existente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recupera informações sobre suplementos  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Remove um suplemento  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Modifica um conjunto existente de configurações de conformidade  <br/> |
|Export-CsPersistentChatData  <br/> |Exporta dados de um banco de dados de Chat Persistente  <br/> |
|Import-CsPersistentChatData  <br/> |Importa dados que foram exportados de uma versão anterior do Lync Server  <br/> |
   

