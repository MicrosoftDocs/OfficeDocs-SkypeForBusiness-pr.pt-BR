---
title: Configuração de Notificação por Push do Cliente Móvel
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: A Notificação por Push e o PNCH (Push Notification Clearing House) são duas partes principais do recurso de mobilidade. A notificação por push é o processo em que uma mensagem é enviada para o PNCH. A mensagem é mantida aqui até que possa ser entregue ao cliente móvel ou o período de tempo de expiração.
---

# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Cliente Móvel: Crie ou Edite a Configuração de Notificação por Push
 
A Notificação por Push e o PNCH (Push Notification Clearing House) são duas partes principais do recurso de mobilidade. A notificação por push é o processo em que uma mensagem é enviada para o PNCH. A mensagem é mantida aqui até que possa ser entregue ao cliente móvel ou o período de tempo de expiração. 
  
> [!NOTE]
> O período de tempo é definido na Casa de Limpeza de Notificação por Push e não é configurável pelo usuário ou pelo administrador da sua implantação. 
  
Para habilitar a Notificação por Push, faça o seguinte:
  
1. **Escopo:** Observe o escopo dessa política. Ele pode ser **Global**, que se aplica a todos os usuários nesta implantação, ou **Site**, que é atribuído apenas aos servidores home no site especificado.
    
    > [!IMPORTANT]
    > As configurações de política aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política é: a política de usuário (mais influência) substitui uma política de Site e, em seguida, uma política de Site substitui uma política Global (menos influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto. 
  
2. Selecione quais serviços de notificação por push você deseja habilitar clicando na caixa de seleção para:
    
   - **Habilitar a notificação** por push da Microsoft habilita a notificação por push para o PNCH baseado em nuvem para Windows Phone com o aplicativo Skype for Business aplicativo
    
   - **Habilitar** a notificação por push da Apple habilita a notificação por push para o Apple PNCH para dispositivos que executam o iOS da Apple (por exemplo, iPhone, iPad) e o uso do aplicativo Skype for Business do Skype for Business
    
3. Quando tiver concluído as edições da política, clique em **Confirmação** para salvar suas alterações. Se você precisar excluir as alterações feitas, selecione **Cancelar**. Nenhuma alteração será salva na política.
    

