---
title: Gerenciar a política de acesso externo da sua organização
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso externo que terão suporte na sua organização.
ms.openlocfilehash: e3feecfffa591df5433ce45526ec236ca6ef8b42
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221655"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Gerenciar a política de acesso externo da sua organização

Depois de implantar um ou mais Servidores de Borda, você deve habilitar os tipos de acesso externo que terão suporte na sua organização.

Por padrão, não há políticas configuradas para suportar o acesso de usuário externo, incluindo o acesso de usuário remoto, acesso de usuário federado, mesmo que você já tenha habilitado o suporte de acesso de usuário externo para sua organização. Para controlar o uso de acesso de usuário externo, você deve configurar uma ou mais políticas, especificando o tipo de acesso de usuário externo suportado para cada política. Os escopos da política a seguir estão disponíveis para criação e configuração. Por padrão, a política global é criada, mas não pode ser excluída.

  - **Política global**   A política global é criada quando você implanta seus Servidores de Borda. Por padrão, nenhuma opção de acesso do usuário externo está habilitada na política global. Para suportar o acesso do usuário externo a nível global, você deve configurar a política global para suportar um ou mais tipos de opções de acesso do usuário externo. A política global se aplica a todos os usuários na sua organização, mas as políticas locais e as políticas de usuário substituem a política global. Ao excluir a política global, ela não é removida. Ao invés, é redefinida para a configuração padrão.

  - **Política de site**   Você pode criar e configurar uma ou mais políticas de site para limitar o suporte ao acesso de usuários externos a sites específicos. A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política. Por exemplo, se você ativar o acesso de usuário remoto na política global, pode especificar uma política de local que o desative para um local específico. Por padrão, a política de local é aplicada a todos os usuários do local, mas você pode atribuir uma política de usuário para substituir a configuração da política de local.

  - **Política de usuário**   Você pode criar e configurar uma ou mais políticas de usuário para limitar o suporte ao acesso de usuário remoto a usuários específicos. A configuração da política de usuário substitui a política global e a do local, mas apenas para usuários específicos aos quais a política de usuário é atribuída. Por exemplo, se você ativar o acesso de usuário remoto na política global e na de local, deve especificar uma política de usuário que a desative e depois atribuir essa política de usuário a usuários específicos. Se você criar uma política de usuário, deve aplicá-la a um ou mais usuários antes que ela surta efeito.


> [!IMPORTANT]  
> As configurações de política aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.


Essas opções incluem os seguintes tipos de acesso externo:

  - **Habilitar comunicações com usuários federados**   Habilite esta opção se desejar oferecer suporte para o acesso de usuários a domínios parceiros federados. Essa configuração configura a capacidade de os usuários se comunicarem com outros domínios federados SIP, bem como provedores hospedados como o Microsoft 365 ou o Office 365. 


  - **Habilitar comunicações com usuários remotos**   Habilite esta opção se desejar que os usuários da sua organização que estejam fora do firewall, como telecomutadores e usuários que estejam viajando, possam se conectar ao Skype for Business Server pela Internet.

  - **Habilitar comunicações com usuários públicos**   Habilite esta opção se desejar que os usuários internos possam se comunicar com os contatos públicos do provedor de mensagens instantâneas.
   

> [!NOTE]  
> Além de habilitar o suporte ao acesso de usuário externo, você também deve configurar políticas para controlar o uso do acesso de usuário externo na organização antes de qualquer tipo de acesso de usuário externo estar disponível para os usuários. Para obter detalhes sobre como criar, configurar e aplicar políticas para acesso de usuário externo, consulte [Habilitar ou desabilitar o acesso de usuário remoto](../access-edge/enable-or-disable-remote-user-access.md).



**Para exibir políticas de acesso externo usando os cmdlets do Windows PowerShell**

  - Você pode exibir políticas de acesso externo usando o Shell de Gerenciamento do Skype for Business Server e o cmdlet **Get-CsExternalAccessPolicy**. Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell. 
    
    Para exibir informações sobre todas as suas políticas de acesso externo, digite o seguinte comando no Shell de Gerenciamento do Lync Server e pressione ENTER:
    
    `Get-CsExternalAccessPolicy`
    
    Esse comando retornará informações parecidas com:
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
