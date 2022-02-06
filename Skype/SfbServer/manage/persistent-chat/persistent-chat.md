---
title: Gerenciar o Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Resumo: Saiba como gerenciar o Servidor de Chat Persistente no Skype for Business Server 2015.'
---

# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Gerenciar o Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar o Servidor de Chat Persistente no Skype for Business Server 2015.
  
Ao configurar o Servidor de Chat Persistente para sua organização, especifique a configuração inicial durante a implantação. No entanto, pode haver momentos em que você deseja alterar como implementar o suporte ao Servidor de Chat Persistente. Por exemplo, talvez seja necessário configurar o suporte e controles do Servidor de Chat Persistente de forma diferente para uma equipe ou grupo específico dentro da sua organização. Esta seção fornece informações e procedimentos para ajudá-lo a personalizar sua implantação do Servidor de Chat Persistente. Para obter detalhes sobre os recursos e funcionalidades que você pode configurar para o Servidor de Chat Persistente, consulte [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Para obter detalhes sobre como implantar o Servidor de Chat Persistente, consulte [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 
  
Você pode gerenciar o Servidor de Chat Persistente usando o Painel de Controle ou usando Windows PowerShell cmdlets. 
  
Para usar o Painel de Controle:
  
1. A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.
    
2. No menu **Iniciar**, selecione o painel de controle Skype for Business Server ou abra uma janela do navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente**.
    
A tabela a seguir resume os Windows PowerShell cmdlets disponíveis para ajudá-lo a gerenciar o Servidor de Chat Persistente. Para obter detalhes sobre sintaxe, incluindo todos os parâmetros disponíveis, [consulte Skype for Business Server Shell de Gerenciamento 2015](../management-shell.md).
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Cria uma nova categoria  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configura configurações para uma categoria existente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recupera informações sobre categorias  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Remove uma categoria  <br/> |
|New-CsPersistentChatRoom  <br/> |Cria uma nova sala de chat  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configura configurações para uma sala existente; atribuir usuários e grupos de usuários à sala  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recupera informações sobre salas  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Limpa uma sala ou mensagens de uma sala  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Remove uma sala  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Remove mensagens de uma sala  <br/> |
|New-CsPersistentChatAddin  <br/> |Cria um novo add-in  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configura configurações para um complemento existente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recupera informações sobre os complementos  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Remove um complemento  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Modifica uma coleção existente de configurações de conformidade  <br/> |
|Export-CsPersistentChatData  <br/> |Exporta dados de um banco de dados de Chat Persistente  <br/> |
|Import-CsPersistentChatData  <br/> |Importa dados que foram exportados de uma versão anterior do Lync Server  <br/> |
   

