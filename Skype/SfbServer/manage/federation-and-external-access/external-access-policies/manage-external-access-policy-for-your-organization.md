---
title: Gerenciar política de acesso externo para sua organização
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Após implantar um ou mais servidores de borda, você deve habilitar os tipos de acesso externo que terão suporte para a sua organização.
ms.openlocfilehash: f1f9798907f70893601a5dfe05b5045e484911e0
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991746"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Gerenciar política de acesso externo para sua organização

Após implantar um ou mais servidores de borda, você deve habilitar os tipos de acesso externo que terão suporte para a sua organização.

Por padrão, não há políticas configuradas para dar suporte a acesso externo a usuários, incluindo acesso de usuário remoto, acesso de usuário federado, mesmo que você já tenha habilitado o acesso de usuário externo à sua organização. Para controlar o uso de acesso de usuário externo, você deve configurar uma ou mais políticas, especificando o tipo de acesso de usuário externo com suporte para cada política. Os seguintes escopos de política estão disponíveis para criação e configuração. Por padrão, a política global é criada, mas não pode ser excluída.

  - **Política global a**   política global é criada quando você implanta seus servidores de borda. Por padrão, nenhuma opção de acesso de usuário externo está habilitada na política global. Para dar suporte ao acesso de usuário externo no nível global, configure a política global para dar suporte a um ou mais tipos de opções de acesso de usuário externo. A política global aplica-se a todos os usuários em sua organização, mas políticas de site e políticas de usuário substituem a política global. Se você excluir a política global, não a removerá. Em vez disso, redefina-o para a configuração padrão.

  - **Política de site**   você pode criar e configurar uma ou mais políticas de site para limitar o suporte ao acesso de usuários externos a sites específicos. A configuração no site substitui a política global, mas somente para o site específico coberto pela política de site. Por exemplo, se você habilitar o acesso de usuário remoto na política global, poderá especificar uma política de site que desabilite o acesso de usuário remoto para um site específico. Por padrão, uma política de site é aplicada a todos os usuários do site, mas você pode atribuir uma política de usuário a um usuário para substituir a configuração de política do site.

  - **Política de usuário**   você pode criar e configurar uma ou mais políticas de usuário para limitar o suporte para acesso de usuário remoto a usuários específicos. A configuração na política de usuário substitui a política global e do site, mas somente para os usuários específicos aos quais a política de usuário está atribuída. Por exemplo, se você habilitar o acesso de usuário remoto na política global e na política do site, poderá especificar uma política de usuário que desabilite o acesso de usuário remoto e atribua essa política de usuário a usuários específicos. Se você criar uma política de usuário, deverá aplicá-la a um ou mais usuários antes de entrar em vigor.


> [!IMPORTANT]  
> As definições de política que são aplicadas em determinado nível de política podem substituir definições que são aplicadas em outro nível. A precedência de política do Skype for Business Server é: a política do usuário (maior influência) substitui uma política do site e, em seguida, uma política de site substitui uma política global (influência mínima). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.


Essas opções incluem os seguintes tipos de acesso externo:

  - **Habilitar comunicações com usuários**   federados habilitá-lo se você quiser dar suporte ao acesso de usuários a domínios de parceiros federados. Essa configuração define a capacidade dos usuários de se comunicarem com outros domínios federados do SIP, bem como provedores hospedados como o Microsoft Office 365. 


  - **Habilitar comunicações com usuários**   remotos habilite essa opção se você quiser que os usuários em sua organização que estão fora do seu firewall, como telecomutadores e usuários que estão viajando, possam se conectar ao Skype for Business Server pela Internet.

  - **Habilitar comunicações com usuários**   públicos habilite essa opção se você quiser que os usuários internos possam se comunicar com contatos públicos do provedor de mensagens de chat.
   

> [!NOTE]  
> Além de habilitar o suporte ao acesso do usuário externo, você também deve configurar políticas para controlar o uso do acesso de usuários externos em sua organização antes que qualquer tipo de acesso de usuário externo esteja disponível para os usuários. Para obter detalhes sobre como criar, configurar e aplicar políticas de acesso de usuário externo, consulte [habilitar ou desabilitar o acesso de usuários remotos](../access-edge/enable-or-disable-remote-user-access.md).



**Para exibir as políticas de acesso externo usando cmdlets do Windows PowerShell**

  - Você pode exibir as políticas de acesso externo usando o Shell de gerenciamento do Skype for Business Server e o cmdlet **Get-CsExternalAccessPolicy** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 
    
    Para ver as informações sobre todas as suas políticas de acesso externo, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
    `Get-CsExternalAccessPolicy`
    
    Este comando retorna informações semelhantes para o seguinte:
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
