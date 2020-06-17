---
title: Mover usuários restantes
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Você pode mover os usuários para a nova implantação do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server. Você deve atender a alguns requisitos para garantir uma transição suave para o Skype for Business Server 2019. Para obter detalhes sobre os pré-requisitos para concluir os procedimentos deste tópico, consulte Configure clients for Migration. Para obter etapas detalhadas sobre como mover usuários, consulte fase 4: mover usuários de teste para o pool piloto.'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753709"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Mover os usuários restantes para o Skype for Business Server 2019

Você pode mover os usuários para a nova implantação do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server. Você deve atender a alguns requisitos para garantir uma transição suave para o Skype for Business Server 2019. Para obter detalhes sobre os pré-requisitos para concluir os procedimentos deste tópico, consulte [Configure clients for Migration](configure-clients-for-migration.md). Para obter etapas detalhadas sobre como mover usuários, consulte [fase 4: mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md).
  
> [!IMPORTANT]
> Você não pode usar o snap-in usuários e computadores do Active Directory ou as ferramentas administrativas herdadas para mover usuários do seu ambiente herdado para o Skype for Business Server 2019. 
  
Quando você mover um usuário para um pool do Skype for Business Server 2019, os dados do usuário serão movidos para o banco de dados back-end associado ao novo pool. 
  
> [!IMPORTANT]
> Isso inclui as reuniões ativas criadas pelo usuário herdado. Por exemplo, se um usuário herdado configurou uma conferência de **reunião** , essa conferência ainda estará disponível no novo pool do Skype for Business Server 2019 depois que o usuário tiver sido movido. Os detalhes para acessar essa a reunião ainda terão a mesma **URL e ID da conferência**. A única diferença é que a conferência agora está hospedada no pool do Skype for Business Server 2019 e não no pool herdado. 
  
> [!NOTE]
> A hospedagem de usuários no Skype for Business Server 2019 não requer a implantação de clientes atualizados ao mesmo tempo. A nova funcionalidade estará disponível aos usuários somente depois que eles atualizarem para o novo software cliente. 
  
### <a name="post-migration-task"></a>Tarefa de migração de pós-instalação

1. Depois de mover os usuários, verifique a política de conferência atribuída a eles. 
    
2. Para garantir que as reuniões organizadas pelos usuários hospedados no Skype for Business Server 2019 funcionem perfeitamente com os usuários federados hospedados na instalação herdada, a política de conferência atribuída aos usuários migrados deve permitir participantes anônimos.
    
3. As políticas de conferência que permitem que os participantes anônimos **permitam que os participantes convidem usuários anônimos** selecionados no painel de controle do Skype for Business Server 2019 e tenham o **AllowAnonymousParticipantsInMeetings** definido como **true** na saída do cmdlet **Get-CsConferencingPolicy** no Shell de gerenciamento do Skype for Business Server. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

