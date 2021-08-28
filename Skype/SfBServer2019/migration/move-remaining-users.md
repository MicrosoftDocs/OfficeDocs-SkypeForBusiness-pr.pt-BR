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
ms.localizationpriority: medium
description: 'Você pode mover usuários para a nova implantação Skype for Business Server 2019 usando o Painel de Controle Skype for Business Server ou o Shell de Gerenciamento Skype for Business Server. Você deve atender a alguns requisitos para garantir uma transição suave para Skype for Business Server 2019. Para obter detalhes sobre os pré-requisitos para concluir os procedimentos neste tópico, consulte Configure clients for migration. Para etapas detalhadas sobre como mover usuários, consulte Fase 4: Mover usuários de teste para o pool piloto.'
ms.openlocfilehash: 60742068bc684470d181593e94615da2a8d79ff6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623103"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Mover usuários restantes para Skype for Business Server 2019

Você pode mover usuários para a nova implantação Skype for Business Server 2019 usando o Painel de Controle Skype for Business Server ou o Shell de Gerenciamento Skype for Business Server. Você deve atender a alguns requisitos para garantir uma transição suave para Skype for Business Server 2019. Para obter detalhes sobre os pré-requisitos para concluir os procedimentos neste tópico, consulte [Configure clients for migration](configure-clients-for-migration.md). Para etapas detalhadas sobre como mover usuários, consulte [Fase 4: Mover](phase-4-move-test-users-to-the-pilot-pool.md)usuários de teste para o pool piloto .
  
> [!IMPORTANT]
> Não é possível usar o snap-in Usuários e Computadores do Active Directory ou as ferramentas administrativas herdados para mover os usuários de seu ambiente herdados para Skype for Business Server 2019. 
  
Quando você move um usuário para um pool de Skype for Business Server 2019, os dados do usuário são movidos para o banco de dados back-end associado ao novo pool. 
  
> [!IMPORTANT]
> Isso inclui as reuniões ativas criadas pelo usuário herdado. Por exemplo, se um usuário herdado tiver configurado uma minha conferência de reunião, essa conferência ainda estará disponível no novo pool Skype for Business Server 2019 após **a** movimentação do usuário. Os detalhes para acessar essa a reunião ainda terão a mesma **URL e ID da conferência**. A única diferença é que a conferência agora está hospedada no pool Skype for Business Server 2019 e não no pool herdado. 
  
> [!NOTE]
> A localização de usuários Skype for Business Server 2019 não exige que você implante clientes atualizados ao mesmo tempo. A nova funcionalidade estará disponível aos usuários somente depois que eles atualizarem para o novo software cliente. 
  
### <a name="post-migration-task"></a>Tarefa pós-migração

1. Depois de mover os usuários, verifique a política de conferência atribuída a eles. 
    
2. Para garantir que as reuniões organizadas pelos usuários no Skype for Business Server 2019 funcionem perfeitamente com usuários federados que estão abrigados na instalação herdada, a política de conferência atribuída aos usuários migrados deve permitir participantes anônimos.
    
3. As políticas de conferência que permitem participantes anônimos têm Permitir que os participantes convidem usuários **anônimos selecionados** no Painel de Controle do Skype for Business Server 2019 e tenham **AllowAnonymousParticipantsInMeetings** definido como **True** na saída do cmdlet **Get-CsConferencingPolicy** no Shell de Gerenciamento Skype for Business Server. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

