---
title: Experiência do usuário durante uma falha de pool no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: Saiba mais sobre o que os usuários podem experimentar quando um pool de front-end falha ou falha durante a recuperação de desastres no Skype for Business Server.
ms.openlocfilehash: 892601267f897050cff635d4d87bb4270e2e0e83
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802321"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Experiência do usuário durante uma falha de pool no Skype for Business Server
 
Saiba mais sobre o que os usuários podem experimentar quando um pool de front-end falha ou falha durante a recuperação de desastres no Skype for Business Server.
  
Se ocorrer um failover de pool, todos os usuários do pool afetado são forçados a sair e entrar no pool de backup. Por um curto período os usuários que entram no pool de backup podem estar no modo de resiliência. No modo de resiliência, os usuários não conseguem executar tarefas que poderiam causar uma alteração persistente no Skype for Business Server, como adicionar um contato. Após a conclusão do failover, todos os usuários podem obter todos os serviços do pool de backup.
  
Quaisquer chamadas, reuniões ou conversas de um usuário serão interrompidas quando o pool falhar, sendo necessário restabelecer essas sessões depois do failover para continuar.
  
Os usuários não são hospedados novamente durante o failover ou o failback. Os usuários que são hospedados em um pool que falha serão atendidos temporariamente pelo pool de backup. Quando o pool de hospedagem é restaurado, o administrador pode efetuar o failback desses usuários para que sejam atendidos pelo pool original, onde eles ainda estão hospedados.
  
Observe que o banco de dados do Location Information Server não é replicado no pool de backup. Como prática recomendada, o administrador deve efetuar regularmente o backup do banco de dados LIS e usar a cópia de backup mais recente para restaurar o banco de dados LIS no pool de backup depois do failover.
  
## <a name="user-experience-during-failover"></a>Experiência do usuário durante o failover

Quando um usuário está em um pool que falha, o usuário é desconectado. Qualquer sessão de ponto a ponto na qual o usuário estava participando é terminada, bem como conferências organizadas por esse usuário. o usuário não pode se conectar até o temporizador de resiliência do registrador expirar ou o administrador iniciar procedimentos de failover, o que ocorrer primeiro. Quando o usuário entrar novamente, isso ocorrerá no pool de backup. Se entrarem antes da conclusão do failover, estarão no modo Resiliência até a conclusão do failover. Somente então o usuário poderá estabelecer novas sessões ou estabelecer novamente sessões anteriores.
  
## <a name="user-experience-during-failback"></a>Experiência do usuário durante failback

O failback de pool pode ocorrer enquanto um usuário afetado é conectado ao pool de backup e o usuário permanece conectado e trabalhando durante o failback. Observe que o processo de failback leva vários minutos para terminar. Para referência, a expectativa é de até 60 minutos para um pool de 20.000 usuários.
  
As seguintes tabelas mostram detalhes sobre como um usuário é afetado durante, bem como depois do failback e também como os usuários em outros pools vêem e interagem com um usuário em um pool que sofre failback. 
  
O termo usuários afetado se refere a qualquer usuário que sofreu failover no pool de hospedagem e está sendo atendido pelo pool de backup. Um usuário originalmente hospedado no pool de backup não é um usuário afetado.
  
**Experiência do usuário para um usuário afetado em um pool em failback**

|**Estado do usuário ou tarefa**|**Durante o failback**|**Após a conclusão do failback**|
|:-----|:-----|:-----|
|Estado do usuário do usuário já conectado  <br/> |O usuário permanece conectado e conectado ao pool de backup. Em algum usuário, o usuário será desconectado e se conectará novamente ao pool inicial original, no modo de resiliência.  <br/> |O usuário permanece conectado e entra no modo normal.  <br/> |
|Novo logon de usuário  <br/> |O usuário pode entrar no pool de Home no modo de resiliência.  <br/> |O usuário pode entrar no pool inicial original em modo normal.  <br/> |
|Conferências em andamento organizadas por um usuário afetado  <br/> |Todas as modalidades de conferência são encerradas. Botão reingressar aparecerá, mas nenhum usuário poderá se reconectar enquanto o usuário afetado estiver no modo de resiliência.  <br/> |Todas as modalidades agora funcionam. Todos os participantes devem clicar para reingressar na conferência.  <br/> |
|Conferências em andamento organizadas por um usuário não afetado  <br/> |A conferência continua e o usuário afetado pode permanecer na conferência. O usuário afetado está restrito ao que ele/ela pode fazer no modo de resiliência.  <br/> |A conferência continua, e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam após o usuário sair do modo de resiliência.  <br/> |
|Agendando ou modificando reuniões agendadas, criando conferências ad hoc  <br/> |Não é possível enquanto o usuário está no modo de resiliência.  <br/> |Disponível para todas as modalidades.  <br/> |
|Presença como vista por outros usuários no mesmo pool  <br/> |Presença desconhecida enquanto o usuário está conectado ao pool de backup durante o modo de resiliência.  <br/> |Mostra o último estado de presença definido pelo usuário e as alterações de presença agora serão refletidas.  <br/> |
|Lista de contatos e disponibilidade do serviço de catálogo de endereços  <br/> |Não disponível  <br/> |Disponível  <br/> |
|Todas as sessões ponto a ponto e modalidades  <br/> |Disponível  <br/> |Disponível  <br/> |
   
**Experiência do usuário para um usuário hospedado em um pool não afetado durante o failback de outro pool**

|**Tarefa do usuário**|**Durante o failback**|**Após a conclusão do failback**|
|:-----|:-----|:-----|
|Visualizando a presença de um usuário afetado  <br/> |Mostra o último estado de presença definido pelo usuário afetado.  <br/> |Trabalhando. Usuários não afetados Veja as atualizações feitas por usuários afetados.  <br/> |
|Conferências em andamento organizadas por um usuário afetado  <br/> |Todas as modalidades de conferência são encerradas.  <br/> |Todas as modalidades agora funcionam. Todos os participantes devem clicar para reingressar na conferência.  <br/> |
|Conferências em andamento organizadas por um usuário não afetado  <br/> |A conferência continua, e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.  <br/> |A conferência continua, e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.  <br/> |
|Todas as sessões ponto a ponto e modalidades  <br/> |Disponível  <br/> |Disponível  <br/> |
   

