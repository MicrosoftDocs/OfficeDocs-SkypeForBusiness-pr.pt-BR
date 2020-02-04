---
title: Cliente móvel criar ou editar configuração de notificação por push
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: Notificação por Push e Push Notification Clearing House (PNCH) são duas partes importantes do recurso de mobilidade. Notificação por Push é o processo no qual uma mensagem é enviada ao PNCH. A mensagem é mantida aqui até que possa ser entregue ao cliente móvel ou até esgotar o tempo limite.
ms.openlocfilehash: eb2fae5e6016fa0e8a28aa2bb750739fd2876f5e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691456"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Cliente móvel: Crie ou edite a Configuração de Notificação por Push
 
Notificação por Push e Push Notification Clearing House (PNCH) são duas partes importantes do recurso de mobilidade. Notificação por Push é o processo no qual uma mensagem é enviada ao PNCH. A mensagem é mantida aqui até que possa ser entregue ao cliente móvel ou até esgotar o tempo limite. 
  
> [!NOTE]
> O período é definido na Push Notification Clearing House e não pode ser configurado pelo usuário ou pelo administrador de sua implantação. 
  
Para habilitar a Notificação por Push, faça o seguinte:
  
1. **Escopo:** observe o escopo dessa política. Pode ser **Global**, que se aplica a todos os usuários nessa implantação, ou **Site**, que são apenas usuários atribuídos a servidores domésticos no site especificado.
    
    > [!IMPORTANT]
    > As definições de política que são aplicadas em determinado nível de política podem substituir definições que são aplicadas em outro nível. A precedência de política é: política de Usuário (maior influência) substitui uma política de Site e esta substitui uma política Global (menor influência). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto. 
  
2. Selecione quais serviços de notificação por push você deseja habilitar clicando na caixa de seleção para:
    
   - **Habilitar a notificação por push da Microsoft** habilitará a notificação por push para o PNCH baseado em nuvem para Windows Phone com o aplicativo Skype for Business
    
   - **Habilitar a notificação por push da Apple** habilitará a notificação por push para o Apple PNCH para dispositivos que executam o Ios da Apple (por exemplo, iPhone, iPad) e usando o aplicativo Skype for Business
    
3. Após concluir as edições da política, clique em  **Confirmar** para salvar suas alterações. Se for necessário excluir as alterações feitas, selecione **Cancelar**. Nenhuma alteração será salva na política.
    

