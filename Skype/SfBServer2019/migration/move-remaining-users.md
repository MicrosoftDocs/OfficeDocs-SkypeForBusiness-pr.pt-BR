---
title: Mover usuários restantes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Você pode mover usuários para o novo Skype para implantação Business Server 2019 usando qualquer um dos Skype para painel de controle do Business Server ou Skype do Shell de gerenciamento do servidor de negócios. Alguns requisitos para garantir uma transição suave para o Skype para Business Server 2019 devem ser atendidos. Para obter detalhes sobre os pré-requisitos para concluir os procedimentos neste tópico, consulte Configure clientes para migração. Para obter etapas detalhadas sobre como mover usuários, consulte a fase 4: mover usuários de teste para o pool piloto.'
ms.openlocfilehash: 9f984b7fac919decce521c6dafc587a4ac86de50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231585"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Mover usuários restantes para Skype para Business Server 2019

Você pode mover usuários para o novo Skype para implantação Business Server 2019 usando qualquer um dos Skype para painel de controle do Business Server ou Skype do Shell de gerenciamento do servidor de negócios. Alguns requisitos para garantir uma transição suave para o Skype para Business Server 2019 devem ser atendidos. Para obter detalhes sobre os pré-requisitos para concluir os procedimentos neste tópico, consulte [Configure clientes para migração](configure-clients-for-migration.md). Para obter instruções detalhadas sobre como mover usuários, consulte [fase 4: mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md).
  
> [!IMPORTANT]
> Você não pode usar o snap-in de computadores e usuários do Active Directory ou as ferramentas administrativas herdadas para mover usuários de seu ambiente herdado para Skype para Business Server 2019. 
  
Quando você mover um usuário para um Skype para Business Server 2019 pool, os dados para o usuário são movidos para o banco de dados de back-end associado ao novo pool. 
  
> [!IMPORTANT]
> Isso inclui as reuniões ativas criadas pelo usuário herdado. Por exemplo, se um usuário herdado tiver configurado uma conferência de **Minha reunião** , conferência continuará disponível no novo Skype para Business Server 2019 pool depois que o usuário foi movido. Os detalhes para acessar essa reunião ainda será a mesma **URL de conferência e a ID de conferência**. A única diferença é que a conferência agora está hospedada no Skype para Business Server 2019 pool e não no pool herdado. 
  
> [!NOTE]
> A hospedagem de usuários em Skype para Business Server 2019 não exige que você implante clientes atualizados ao mesmo tempo. Nova funcionalidade estará disponível para os usuários somente quando eles tem atualizado para o novo software cliente. 
  
### <a name="post-migration-task"></a>Tarefas pós-migração

1. Depois de mover usuários, verifique se a política de conferência atribuída a eles. 
    
2. Para garantir que as reuniões organizadas pelos usuários hospedagem no Skype Business Server 2019 trabalho perfeitamente com os usuários federados hospedados no install herdado, a política de conferência atribuída aos usuários migrados deve permitir participantes anônimos.
    
3. Políticas de conferência que permitem participantes anônimos tem **Permitir que os participantes convidem usuários anônimos** selecionados no Skype para painel de controle do Business Server 2019 e tem **AllowAnonymousParticipantsInMeetings** definem como **True** no saída do cmdlet **Get-CsConferencingPolicy** no Skype do Shell de gerenciamento do servidor de negócios. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

