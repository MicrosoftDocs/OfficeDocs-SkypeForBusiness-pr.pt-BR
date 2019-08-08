---
title: Mover usuários restantes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Você pode mover os usuários para a nova implantação do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server. Você deve atender a alguns requisitos para garantir uma transição tranqüila para o Skype for Business Server 2019. Para obter detalhes sobre pré-requisitos para completar os procedimentos deste tópico, consulte Configurar clientes para migração. Para ver as etapas detalhadas sobre como mover usuários, consulte fase 4: mover usuários de teste para o pool piloto.'
ms.openlocfilehash: 8c12ca52e162c4317dabc59d5de9b74082730882
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244562"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Mover os usuários restantes para o Skype for Business Server 2019

Você pode mover os usuários para a nova implantação do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server. Você deve atender a alguns requisitos para garantir uma transição tranqüila para o Skype for Business Server 2019. Para obter detalhes sobre pré-requisitos para completar os procedimentos deste tópico, consulte [configurar clientes para migração](configure-clients-for-migration.md). Para ver as etapas detalhadas sobre como mover usuários, consulte [fase 4: mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md).
  
> [!IMPORTANT]
> Você não pode usar o snap-in usuários e computadores do Active Directory ou as ferramentas administrativas herdadas para mover os usuários do seu ambiente herdado para o Skype for Business Server 2019. 
  
Quando você move um usuário para um pool do Skype for Business Server 2019, os dados do usuário são movidos para o banco de dados back-end associado ao novo pool. 
  
> [!IMPORTANT]
> Isso inclui as reuniões ativas criadas pelo usuário herdado. Por exemplo, se um usuário herdado configurou uma conferência de **reunião** , essa conferência ainda estará disponível no novo pool do Skype for Business Server 2019 após o usuário ter sido movido. Os detalhes para acessar a reunião ainda serão a mesma **URL de conferência e ID de conferência**. A única diferença é que a conferência agora está hospedada no pool do Skype for Business Server 2019 e não no pool herdado. 
  
> [!NOTE]
> A hospedagem de usuários no Skype for Business Server 2019 não requer que você implante clientes atualizados ao mesmo tempo. A nova funcionalidade estará disponível para os usuários somente quando tiverem atualizado para o novo software cliente. 
  
### <a name="post-migration-task"></a>Tarefa pós-migração

1. Depois de mover os usuários, verifique a política de conferência atribuída a ele. 
    
2. Para garantir que as reuniões organizadas por usuários hospedados no Skype for Business Server 2019 trabalhe perfeitamente com usuários federados que são hospedados na instalação herdada, a política de conferência atribuída aos usuários migrados deve permitir participantes anônimos.
    
3. As políticas de conferência que permitem aos participantes anônimos **permitir que os participantes convidem usuários anônimos** selecionados no painel de controle do Skype for Business Server 2019 e ter o **AllowAnonymousParticipantsInMeetings** definido como **true** na saída do cmdlet **Get-CsConferencingPolicy** no Shell de gerenciamento do Skype for Business Server. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

