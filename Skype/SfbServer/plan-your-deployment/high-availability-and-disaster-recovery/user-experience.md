---
title: Experiência do usuário durante falha no pool Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: Saiba mais sobre o que os usuários experimentam quando um pool de Front-End falha ou falha durante a recuperação de desastres Skype for Business Server.
ms.openlocfilehash: 4fb48423d09a1d891e3eb5ae209059cb6722bf81
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835139"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Experiência do usuário durante falha no pool Skype for Business Server
 
Saiba mais sobre o que os usuários experimentam quando um pool de Front-End falha ou falha durante a recuperação de desastres Skype for Business Server.
  
Se um pool falhar, todos os usuários no pool afetado serão forçados a sair e entrar no pool de backup. Por um breve período, os usuários que entraram no pool de backup podem estar no modo de resiliência. No modo resiliência, os usuários não conseguem executar tarefas que causam uma alteração persistente no Skype for Business Server, como adicionar um contato. Depois que o failover for concluído, todos os usuários poderão obter todos os serviços do pool de backup.
  
Todas as chamadas, reuniões ou conversas que um usuário tem quando o pool falha são interrompidas e o usuário deve restabelecer essas sessões após o failover para continuar.
  
Os usuários não são recontrados durante o failover ou o failback. Os usuários que estão em um pool com falha serão temporariamente atendidos pelo pool de backup. Quando o pool inicial é restaurado, o administrador pode fazer fail back desses usuários para serem atendidos pelo pool original, onde eles ainda estão em casa.
  
Observe que o banco de dados do Servidor de Informações de Local não é replicado para o pool de backup. Para prática prática prática, o administrador deve fazer backup regular do banco de dados LIS e usar a cópia de backup mais recente para restaurar o banco de dados LIS no pool de backup após o failover.
  
## <a name="user-experience-during-failover"></a>Experiência do usuário durante o failover

Quando um usuário está em um pool que falha, o usuário é desconectado. Qualquer sessão ponto a ponto em que o usuário estava participando é encerrada, assim como as conferências organizadas por esse usuário. O usuário não poderá fazer logoff até que o temporizador de resiliência do registrador expire ou o administrador inicie os procedimentos de failover, o que ocorrer primeiro. Quando o usuário fizer logoff de volta, ele fará logoff no pool de backup. Se eles fizerem logoff antes da conclusão do failover, eles estarão no modo resiliência até que o failover seja concluído. Somente então um usuário pode estabelecer novas sessões ou restabelecer sessões anteriores.
  
## <a name="user-experience-during-failback"></a>Experiência do usuário durante o failback

O failback do pool pode acontecer enquanto um usuário afetado está conectado ao pool de backup e o usuário permanece conectado e funcionando durante o failback. Observe que o processo de failback leva vários minutos para ser concluído. Como referência, espera-se que leve até 60 minutos para um pool de 20 mil usuários.
  
As tabelas a seguir mostram mais detalhes sobre como um usuário é afetado durante e após o failback e também como os usuários em outros pools veem e interagem com um usuário em um pool que está sendo reprovado. 
  
O termo usuário afetado refere-se a qualquer usuário que falhou no pool 1 e está sendo atendido pelo pool de backup. Um usuário originalmente abrigado no pool de backup não é um usuário afetado.
  
**Experiência do usuário para um usuário afetado em um pool no Failback**

|**Estado do usuário ou tarefa**|**Durante o failback**|**Após a conclusão do failback**|
|:-----|:-----|:-----|
|Estado do usuário do usuário já conectado  <br/> |O usuário permanece conectado e conectado ao pool de backup. Em algum momento, o usuário será assinado e entrará novamente no pool inicial original, no modo Resiliência.  <br/> |O usuário permanece entrando e entrando no modo normal.  <br/> |
|Novo logor de usuário  <br/> |O usuário pode entrar no pool 1 no modo Resiliência.  <br/> |O usuário pode entrar no pool inicial original no modo regular.  <br/> |
|Conferências em andamento organizadas pelo usuário afetado  <br/> |Todas as modalidades de conferência são encerradas. O botão Reunir aparecerá, mas nenhum usuário poderá voltar enquanto o usuário afetado estiver no modo Resiliência.  <br/> |Todas as modalidades agora funcionam. Cada participante precisa clicar para voltar à conferência.  <br/> |
|Conferências em andamento organizadas por usuários não afetados  <br/> |A conferência continua e o usuário afetado pode permanecer na conferência. O usuário afetado está restrito ao que pode fazer no modo resiliência.  <br/> |A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam depois que o usuário sai do modo resiliência.  <br/> |
|Agendar ou modificar reuniões agendadas, criar conferências ad hoc  <br/> |Não é possível enquanto o usuário estiver no modo Resiliência.  <br/> |Disponível para todas as modalidades.  <br/> |
|Presença vista por outros usuários no mesmo pool  <br/> |Presença desconhecida enquanto o usuário está entrando no pool de backup durante o modo Resiliência.  <br/> |Mostra o último estado de presença definido pelo usuário e as alterações de presença agora serão refletidas.  <br/> |
|Lista de contatos e disponibilidade do Serviço de Livro de Endereços  <br/> |Não disponível  <br/> |Disponível  <br/> |
|Todas as sessões ponto a ponto e modalidades  <br/> |Disponível  <br/> |Disponível  <br/> |
   
**User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool**

|**Tarefa do usuário**|**Durante o failback**|**Após a conclusão do failback**|
|:-----|:-----|:-----|
|Exibindo a presença do usuário afetado  <br/> |Mostra o último estado de presença definido pelo usuário afetado.  <br/> |Trabalhando. Usuários não afetados veem atualizações feitas por usuários afetados.  <br/> |
|Conferências em andamento organizadas pelo usuário afetado  <br/> |Todas as modalidades de conferência são encerradas.  <br/> |Todas as modalidades agora funcionam. Cada participante precisa clicar para voltar à conferência.  <br/> |
|Conferências em andamento organizadas por usuários não afetados  <br/> |A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.  <br/> |A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.  <br/> |
|Todas as sessões ponto a ponto e modalidades  <br/> |Disponível  <br/> |Disponível  <br/> |
   

