---
title: Experiência do usuário durante falha do pool no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: Saiba mais sobre o que os usuários experimentam quando um pool de Front-End falha ou falha durante a recuperação de desastre no Skype for Business Server.
ms.openlocfilehash: 137ad9076febccb272e88e457ee56e6474cff107
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809901"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Experiência do usuário durante falha do pool no Skype for Business Server
 
Saiba mais sobre o que os usuários experimentam quando um pool de Front-End falha ou falha durante a recuperação de desastre no Skype for Business Server.
  
Se um pool for failed over, todos os usuários no pool afetado serão forçados a sair e entrar no pool de backup. Por um breve período, os usuários que entrarem no pool de backup poderão estar no modo de resiliência. No modo de resiliência, os usuários não conseguem realizar tarefas que causaiam uma alteração persistente no Skype for Business Server, como adicionar um contato. Depois que o failover for concluído, todos os usuários poderão obter todos os serviços do pool de backup.
  
Todas as chamadas, reuniões ou conversas que um usuário tem quando o pool falha são interrompidas e o usuário deve restabelecer essas sessões após o failover para continuar.
  
Os usuários não são rehomed durante failover ou failback. Os usuários que estão em um pool que falha serão temporariamente atendidos pelo pool de backup. Quando o pool inicial é restaurado, o administrador pode fazer fail back desses usuários para serem atendidos pelo pool original, onde eles ainda estão.
  
Observe que o banco de dados do Servidor de Informações de Local não é replicado para o pool de backup. Para melhor prática, o administrador deve fazer regularmente o backup do banco de dados LIS e usar a cópia de backup mais recente para restaurar o banco de dados LIS no pool de backup após o failover.
  
## <a name="user-experience-during-failover"></a>Experiência do usuário durante failover

Quando um usuário está em um pool que falha, ele é desconectado. Qualquer sessão ponto a ponto em que o usuário estava participando é encerrada, assim como as conferências organizadas por esse usuário. O usuário não pode entrar novamente até que o temporizador de resiliência do registrador expire ou o administrador inicie os procedimentos de failover, o que ocorrer primeiro. Quando o usuário entrar novamente, ele fará logoff no pool de backup. Se eles fizerem logoff antes da conclusão do failover, eles estarão no modo de Resiliência até que o failover seja concluído. Somente então um usuário poderá estabelecer novas sessões ou restabelecer sessões anteriores.
  
## <a name="user-experience-during-failback"></a>Experiência do usuário durante failback

O failback de pool pode ocorrer enquanto um usuário afetado está conectado ao pool de backup, e o usuário permanece conectado e trabalhando durante o failback. Observe que o processo de failback leva vários minutos para ser concluído. Como referência, espera-se que leve até 60 minutos para um pool de 20 mil usuários.
  
As tabelas a seguir mostram mais detalhes sobre como um usuário é afetado durante e após o failback e também como os usuários em outros pools veem e interagem com um usuário em um pool que está sendo failback. 
  
O termo afetado do usuário se refere a qualquer usuário que tenha feito o failed over do pool de residência e que está sendo atendido pelo pool de backup. Um usuário originalmente abrigado no pool de backup não é um usuário afetado.
  
**Experiência do usuário para um usuário afetado em um pool em failback**

|**Estado ou tarefa do usuário**|**Durante o failback**|**Após a conclusão do failback**|
|:-----|:-----|:-----|
|Estado do usuário do usuário já conectado  <br/> |O usuário permanece conectado e conectado ao pool de backup. Em algum momento, o usuário será desalistada e entrar novamente no pool base original, no modo de resiliência.  <br/> |O usuário permanece e entra no modo normal.  <br/> |
|Novo usuário fazendo logo in  <br/> |O usuário pode entrar no pool base no modo resiliência.  <br/> |O usuário pode entrar no pool inicial original no modo regular.  <br/> |
|Conferências contínuas organizadas pelo usuário afetado  <br/> |Todas as modalidades de conferência são encerradas. O botão Reesessar será exibido, mas nenhum usuário poderá reesutar enquanto o usuário afetado estiver no modo resiliência.  <br/> |Todas as modalidades agora funcionam. Todos os participantes precisam clicar para participar novamente da conferência.  <br/> |
|Conferências contínuas organizadas por usuário não afetado  <br/> |A conferência continua e o usuário afetado pode permanecer na conferência. O usuário afetado está restrito ao que pode fazer no modo resiliência.  <br/> |A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam depois que o usuário sai do modo resiliência.  <br/> |
|Agendando ou modificando reuniões agendadas, criando conferências ad-hoc  <br/> |Não é possível enquanto o usuário está no modo resiliência.  <br/> |Disponível para todas as modalidades.  <br/> |
|Presença vista por outros usuários no mesmo pool  <br/> |Presença desconhecida enquanto o usuário está entrando no pool de backup durante o modo de resiliência.  <br/> |Mostra o último estado de presença definido pelo usuário, e as alterações de presença agora serão refletidas.  <br/> |
|Lista de contatos e disponibilidade do Serviço de Agenda  <br/> |Não disponível  <br/> |Disponível  <br/> |
|Todas as sessões ponto a ponto e modalidades  <br/> |Disponível  <br/> |Disponível  <br/> |
   
**Experiência do usuário para um usuário que está em um pool não afetado durante o failback de outro pool**

|**Tarefa do usuário**|**Durante o failback**|**Após a conclusão do failback**|
|:-----|:-----|:-----|
|Exibindo a presença do usuário afetado  <br/> |Mostra o último estado de presença definido pelo usuário afetado.  <br/> |Trabalhando. Os usuários não afetados veem as atualizações feitas pelos usuários afetados.  <br/> |
|Conferências contínuas organizadas pelo usuário afetado  <br/> |Todas as modalidades de conferência são encerradas.  <br/> |Todas as modalidades agora funcionam. Todos os participantes precisam clicar para participar novamente da conferência.  <br/> |
|Conferências contínuas organizadas por usuário não afetado  <br/> |A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.  <br/> |A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.  <br/> |
|Todas as sessões ponto a ponto e modalidades  <br/> |Disponível  <br/> |Disponível  <br/> |
   

