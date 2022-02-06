---
title: Configuração de notificação por push do cliente móvel
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Para configurar as Notificações por push da Microsoft e asNotificações por push da Apple, é necessário criar uma política para definir quais tipos de notificação por push você precisa.'
---

# <a name="mobile-client-push-notification-configuration"></a>Cliente Móvel: Configuração de Notificação por Push
 
Para configurar as **Notificações por push da Microsoft** e as **Notificações por push da Apple**, é necessário criar uma política para definir quais tipos de notificação por push você precisa.
  
Na tela de configuração principal, é possível clicar em **Atualizar** para atualizar e preencher novamente a lista de políticas. Uma caixa de pesquisa é fornecida para reduzir a lista de políticas exibidas. À medida que você digita o nome que está procurando, a lista de políticas é reduzida automaticamente.
  
> [!IMPORTANT]
> As configurações de política aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política é: a política de usuário (mais influência) substitui uma política de Site e, em seguida, uma política de Site substitui uma política Global (menos influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto. 
  
Há duas seleções disponíveis para criação e edição de política:
  
1. **Novo**: clique para criar uma nova política. É necessário fornecer um site ao qual aplicar a política. Em seguida, você define as configurações para a notificação por push. Para **Configuração da Notificação por Push**, é possível apenas criar políticas para Sites que você já criou.
    
2. **Editar**: selecione uma política e clique em Editar para selecionar uma ação de um menu suspenso. Você pode apenas editar sites que já criou ou editar a Política Global:
    
   - **Mostrar detalhes…**: exibe informações sobre a política atualmente selecionada. Você poderá fazer alterações na política existente.
    
   - **Selecionar tudo**: se você tiver algumas políticas e precisar selecionar todas elas, clique em Selecionar tudo
    
   - **Excluir**: removerá a política selecionada. Usar **Selecionar tudo** e **Excluir** removerá todas as políticas
    
     > [!NOTE]
     > Não é possível excluir a política **Global** padrão. Se você tentar exclui-la, receberá uma notificação de que a política Global retomou seus valores padrão (ou seja, todas as configurações foram desmarcadas), mas a política não pode ser removida.
  
A criação de uma nova política ou edição de uma política existente está associada a duas ações:
  
- **Commit** A ação de confirmação cria ou atualiza a política e salva as alterações
    
- **Cancelar** A ação cancel descarta todas as alterações feitas desde a última ação de confirmação. Se você cancelar, quaisquer alterações feitas serão perdidas.
    
Duas configurações são possíveis para a **Configuração de Notificação por Push**. As configurações são associadas aos serviços de notificação por push da Microsoft e da Apple. Habilite a notificação por push para qualquer um desses serviços marcando a caixa de seleção ao lado do nome do serviço. É possível desmarcar a caixa de seleção clicando nela. Depois de fazer suas seleções, confirme ou cancele. Clicar em confirmar salvará as alterações na política.
  

