---
title: Gerenciar Servidor de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Resumo: Saiba como gerenciar o servidor de Chat persistente no Skype para Business Server 2015.'
ms.openlocfilehash: 294c6bcecbbfb57bb8d2a6a785cdf20775119510
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Gerenciar Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar o servidor de Chat persistente no Skype para Business Server 2015.
  
Quando você configura o servidor de Chat persistente para sua organização, você pode especificar a configuração inicial durante a implantação. No entanto, pode haver ocasiões em que você deseja alterar como implementar o suporte do servidor de Chat persistente. Por exemplo, você pode precisar configurar o suporte do servidor de Chat persistente e controles de forma diferente para uma equipe específico ou um grupo dentro da sua organização. Esta seção fornece informações e procedimentos para ajudá-lo a personalizar sua implantação de servidor de Chat persistente. Para obter detalhes sobre os recursos e funcionalidade que você pode definir para o servidor de Chat persistente, consulte [Plan for Persistent Chat Server in Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Para obter detalhes sobre como implantar o servidor de Chat persistente, consulte [Implantar Persistent Chat Server in Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
  
Você pode gerenciar o servidor de Chat persistente usando o painel de controle ou usando cmdlets do Windows PowerShell. 
  
Para usar o Painel de Controle:
  
1. A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.
    
2. No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.
    
3. Na barra de navegação à esquerda, clique em **Chat persistente**.
    
A tabela a seguir resume os cmdlets do Windows PowerShell disponíveis para ajudá-lo a gerenciar o servidor de Chat persistente. Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros disponíveis, consulte [Skype do Shell de gerenciamento do Business Server 2015](../management-shell.md).
  

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
   

