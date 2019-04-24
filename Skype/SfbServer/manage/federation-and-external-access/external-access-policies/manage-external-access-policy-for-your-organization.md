---
title: Gerenciar política de acesso externo para sua organização
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de implantar um ou mais servidores de borda, você deverá habilitar os tipos de acesso externo que serão suportados pela sua organização.
ms.openlocfilehash: bdc1a87476849a6e8383d5561af6e1b3af477869
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199881"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Gerenciar política de acesso externo para sua organização

Depois de implantar um ou mais servidores de borda, você deverá habilitar os tipos de acesso externo que serão suportados pela sua organização.

Por padrão, não há nenhuma diretiva configurada para oferecer suporte ao acesso de usuário externo, incluindo o acesso de usuário remoto, acesso de usuário federado, mesmo se você já tiver ativado o suporte ao acesso de usuário externo para sua organização. Para controlar o uso de acesso de usuário externo, você deve configurar uma ou mais políticas, especificando o tipo de suporte para cada política de acesso de usuário externo. Os escopos de política a seguir estão disponíveis para criação e configuração. Por padrão, a política Global é criada, mas não pode ser excluída.

  - **Política global**   a política global é criada quando você implanta os servidores de borda. Por padrão, não há opções de acesso de usuário externo estão habilitadas na política global. Para suportar o acesso de usuário externo no nível global, você deve configurar a política global para oferecer suporte a um ou mais tipos de opções de acesso de usuário externo. A política global se aplica a todos os usuários em sua organização, mas as políticas de site e políticas de usuário substituem a política global. Se você excluir a política global, você não removê-lo. Em vez disso, redefini-lo para a configuração padrão.

  - **Política de site**   você pode criar e configurar uma ou mais políticas de site para limitar o suportam para acesso de usuário externo a sites específicos. A configuração no site substitui a política global, mas somente para o site específico coberto pela política de site. Por exemplo, se você habilitar o acesso de usuário remoto na política global, você pode especificar uma política de site que desabilita o acesso de usuário remoto para um site específico. Por padrão, uma política de site é aplicada a todos os usuários do site, mas você pode atribuir uma política de usuário a um usuário para substituir a configuração de política de site.

  - **Política de usuário**   você pode criar e configurar uma ou mais políticas de usuário para limitar o suportam para acesso de usuário remoto a usuários específicos. A configuração na política de site e substituições de diretiva de usuário global, mas somente para os usuários específicos aos quais a política de usuário é atribuída. Por exemplo, se você habilitar o acesso de usuário remoto na política global e política de site, você pode especificar uma política de usuário que desabilita o acesso de usuário remoto e, em seguida, atribuir essa política de usuário para usuários específicos. Se você criar uma política de usuário, você deverá aplicá-la a um ou mais usuários antes que ele entra em vigor.


> [!IMPORTANT]  
> As definições de política que são aplicadas em determinado nível de política podem substituir definições que são aplicadas em outro nível. Skype para precedência da diretiva Business Server é: política de usuário (maior influência) substitui uma política de Site e, em seguida, uma política de Site substitui uma política Global (influência mínimos). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.


Essas opções incluem os seguintes tipos de acesso externo:

  - **Habilitar comunicações com usuários federados**   habilite isso se você deseja oferecer suporte ao acesso de usuário para domínios de parceiros federados. Essa definição configura a capacidade dos usuários se comuniquem com os outros domínios, bem como provedores hospedados, como o Microsoft Office 365 federados de SIP. 


  - **Habilitar comunicações com usuários remotos**   habilite essa opção se quiser que os usuários em sua organização que estão fora do firewall, como funcionários remotos e usuários que estiver viajando, possam se conectar ao Skype para Business Server pela Internet.

  - **Habilitar comunicações com usuários públicos**   habilite essa opção se quiser que os usuários internos poderão se comunicar com contatos de provedor IM públicos.
   

> [!NOTE]  
> Além de habilitar o acesso de usuário externo, suporte, você também deve configurar políticas para controlar o uso de acesso de usuário externo em sua organização antes de qualquer tipo de acesso de usuário externo está disponível para usuários. Para obter detalhes sobre como criar, configurar e aplicar políticas de acesso de usuário externo, consulte [Habilitar ou desabilitar o acesso de usuário remoto](../access-edge/enable-or-disable-remote-user-access.md).



**Para exibir as políticas de acesso externo usando cmdlets do Windows PowerShell**

  - Você pode exibir as políticas de acesso externo usando Skype para o Shell de gerenciamento de servidor de negócios e o cmdlet **Get-CsExternalAccessPolicy** . Você pode executar esse cmdlet a partir do Skype do Shell de gerenciamento do servidor de negócios ou uma sessão remota do Windows PowerShell. 
    
    Para exibir informações sobre todas as suas políticas de acesso externo, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
    `Get-CsExternalAccessPolicy`
    
    Este comando retorna informações semelhantes para o seguinte:
    
    ```
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
