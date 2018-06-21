---
title: Configuração de notificação de Push do cliente móvel
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Para configurar as notificações de push da Microsoft e notificações de push do Apple, você deve criar uma política para definir quais tipos de notificação por push você exige.
ms.openlocfilehash: 5570ab2f25359d847c6b594f36f865a1c37e170e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19971239"
---
# <a name="mobile-client-push-notification-configuration"></a>Cliente móvel: Configuração de notificação por Push
 
Para configurar as **notificações de push da Microsoft** e **notificações de push do Apple**, você deve criar uma política para definir quais tipos de notificação de push você requer.
  
Na tela Configuração principal, você pode clicar **Refresh** para atualizar e popular novamente a lista de políticas. Uma caixa de pesquisa é fornecida para restringir a lista de diretivas exibidas. Conforme você digita o nome que você está procurando, lista de políticas estreita automaticamente.
  
> [!IMPORTANT]
> As definições de política que são aplicadas em determinado nível de política podem substituir definições que são aplicadas em outro nível. A precedência de política é: política de Usuário (maior influência) substitui uma política de Site e esta substitui uma política Global (menor influência). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto. 
  
Há duas seleções estão disponíveis para criação de políticas e edição:
  
1. **New**: clique para criar uma nova política. Você deve fornecer um site para a política seja aplicada a. Em seguida, você definir as configurações da notificação de push. Para **Configuração de notificação por Push**, você só pode criar políticas para Sites que você criou.
    
2. **Editar**: selecione uma política e clique em Editar para selecionar uma ação na lista suspensa. Você só pode editar os sites que você já criou ou editar a política Global:
    
  - **Mostrar detalhes …**: exibe informações sobre a política selecionada no momento. Você poderá fazer alterações à diretiva existente.
    
  - **Selecionar tudo**: se você tiver algumas políticas e precisa selecionar todas elas, clique em Selecionar tudo
    
  - **Excluir**: removerá a política selecionada. O uso de **Selecionar tudo** e **Excluir** removerá todas as diretivas
    
    > [!NOTE]
    > Você não pode excluir a política **Global** de padrão. Se você tentar excluí-lo, você será notificado se a política Global foi retornada para os valores padrão (ou seja, todas as configurações estão desmarcadas), mas a política não pode ser removida.
  
Criando uma nova política ou editar uma política existente está associado a duas ações:
  
- **Confirmar** A ação de confirmação cria ou atualiza a política e salva as alterações
    
- **Cancelar** A ação Cancelar descarta quaisquer alterações que tenham sido feitas desde a última ação de confirmação. Se você cancelar, quaisquer alterações feitas serão perdidas.
    
Duas configurações são possíveis para a **Configuração de notificação por Push**. As configurações estão associadas com os serviços de notificação por push para Microsoft e Apple. Você pode habilitar notificação de envio para qualquer serviço marcando a caixa de seleção ao lado do nome do serviço. Você pode desmarcar a caixa de seleção, selecionando-o para desmarcá-la. Depois de fazer suas seleções, você confirmar ou Cancelar. Quando você clica em Confirmar salvará as alterações à política.
  

