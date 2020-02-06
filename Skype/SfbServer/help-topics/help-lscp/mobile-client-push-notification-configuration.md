---
title: Configuração de notificação por push de cliente móvel
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Para configurar as notificações por push da Microsoft e as notificações por push da Apple, você deve criar uma política para definir quais tipos de notificação por push são necessárias.
ms.openlocfilehash: 3fde99c3f026f87197492417cd10611d96f7e20e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822654"
---
# <a name="mobile-client-push-notification-configuration"></a>Cliente Móvel: Configuração de Notificação por Push
 
Para configurar as notificações por push da **Microsoft** e as **notificações por push da Apple**, você deve criar uma política para definir quais tipos de notificação por push são necessárias.
  
Na tela principal de configuração, você pode clicar em **Atualizar** para atualizar e preencher novamente a lista de políticas. Uma caixa de pesquisa é fornecida para restringir a lista de políticas exibidas. À medida que você digita o nome que está procurando, a lista de políticas é limitada automaticamente.
  
> [!IMPORTANT]
> As definições de política que são aplicadas em determinado nível de política podem substituir definições que são aplicadas em outro nível. A precedência de política é: política de Usuário (maior influência) substitui uma política de Site e esta substitui uma política Global (menor influência). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto. 
  
Duas seleções estão disponíveis para criação e edição de políticas:
  
1. **Novo**: clique para criar uma nova política. Você deve fornecer um site ao qual a política se aplica. Em seguida, defina as configurações para a notificação por push. Para a **configuração de notificação por push**, você só pode criar políticas para sites que já criou.
    
2. **Editar**: selecione uma política e clique em Editar para selecionar uma ação de uma lista suspensa. Você só pode editar sites que já criou ou editar a política global:
    
   - **Mostrar detalhes...**: exibe informações sobre a política selecionada no momento. Você poderá fazer alterações na política existente.
    
   - **Selecionar tudo**: se você tiver uma quantidade de políticas e precisar selecionar todas as políticas, clique em selecionar tudo
    
   - **Excluir**: a política selecionada será removida. Usar **selecionar tudo** e **excluir** irá remover todas as políticas
    
     > [!NOTE]
     > Não é possível excluir a política **global** padrão. Se você tentar excluí-lo, você será notificado de que a política global foi retornada para os valores padrão (ou seja, todas as configurações são desmarcadas), mas a política não pode ser removida.
  
A criação de uma nova política ou edição de uma política existente é associada a duas ações:
  
- **Confirmar** A ação confirmar cria ou atualiza a política e salva as alterações
    
- **Cancelar** A ação cancelar descarta todas as alterações feitas desde a última ação de confirmação. Se você cancelar, todas as alterações feitas serão perdidas.
    
Duas configurações são possíveis para a **configuração de notificação por push**. As configurações são associadas aos serviços de notificação por push para a Microsoft e para a Apple. Para habilitar a notificação por push para qualquer um dos serviços, marque a caixa de seleção ao lado do nome do serviço. Você pode desmarcar a caixa de seleção selecionando-a para desmarcá-la. Depois de fazer suas seleções, você pode confirmar ou cancelar. Clicar em confirmar irá salvar as alterações na política.
  

