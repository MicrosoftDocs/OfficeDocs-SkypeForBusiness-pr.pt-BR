---
title: Experiência do usuário durante falha do pool no Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: Saiba mais sobre o que os usuários experimentam quando um pool de Front-End failover ou falha durante a recuperação de desastres em Skype para Business Server.
ms.openlocfilehash: 741eb40d0bf4ee615d68d05ab6b9543b6f65474b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001186"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Experiência do usuário durante falha do pool no Skype para Business Server
 
Saiba mais sobre o que os usuários experimentam quando um pool de Front-End failover ou falha durante a recuperação de desastres em Skype para Business Server.
  
Se ocorrer um failover de pool, todos os usuários do pool afetado são forçados a sair e entrar no pool de backup. Por um curto período os usuários que entram no pool de backup podem estar no modo de resiliência. No modo de resiliência, os usuários não conseguem realizar tarefas que fará com que uma alteração persistente no Skype para Business Server, como a adição de um contato. Após a conclusão do failover, todos os usuários podem obter todos os serviços do pool de backup.
  
Quaisquer chamadas, reuniões ou conversas de um usuário serão interrompidas quando o pool falhar, sendo necessário restabelecer essas sessões depois do failover para continuar.
  
Os usuários não são hospedados novamente durante o failover ou o failback. Os usuários que são hospedados em um pool que falha serão atendidos temporariamente pelo pool de backup. Quando o pool de hospedagem é restaurado, o administrador pode efetuar o failback desses usuários para que sejam atendidos pelo pool original, onde eles ainda estão hospedados.
  
Observe que o banco de dados do Location Information Server não é replicado no pool de backup. Como prática recomendada, o administrador deve efetuar regularmente o backup do banco de dados LIS e usar a cópia de backup mais recente para restaurar o banco de dados LIS no pool de backup depois do failover.
  
## <a name="user-experience-during-failover"></a>Experiência do usuário durante o failover

Quando um usuário está em um pool que falha, o usuário é desconectado. Qualquer sessão de ponto a ponto na qual o usuário estava participando é terminada, bem como conferências organizadas por esse usuário. o usuário não pode se conectar até o temporizador de resiliência do registrador expirar ou o administrador iniciar procedimentos de failover, o que ocorrer primeiro. Quando o usuário entrar novamente, isso ocorrerá no pool de backup. Se entrarem antes da conclusão do failover, estarão no modo Resiliência até a conclusão do failover. Somente então o usuário poderá estabelecer novas sessões ou estabelecer novamente sessões anteriores.
  
## <a name="user-experience-during-failback"></a>Experiência do usuário durante failback

O failback de pool pode ocorrer enquanto um usuário afetado é conectado ao pool de backup e o usuário permanece conectado e trabalhando durante o failback. Observe que o processo de failback leva vários minutos para terminar. Para referência, a expectativa é de até 60 minutos para um pool de 20.000 usuários.
  
As seguintes tabelas mostram detalhes sobre como um usuário é afetado durante, bem como depois do failback e também como os usuários em outros pools vêem e interagem com um usuário em um pool que sofre failback. 
  
O termo usuários afetado se refere a qualquer usuário que sofreu failover no pool de hospedagem e está sendo atendido pelo pool de backup. Qualquer usuário hospedado originalmente no pool de backup não é um usuário afetado.
  
**Experiência do usuário para um usuário afetado em um pool failback**

|**Estado ou tarefa do usuário**|**Durante o failback**|**Depois da conclusão do failback**|
|:-----|:-----|:-----|
|Estado do usuário já conectado  <br/> |O usuário permanece registrado e conectado ao pool de backup. Em algum momento o usuário será desconectado e conectado ao pool de hospedagem original, no modo Resiliência.  <br/> |O usuário permanece conectado e entra no modo normal.  <br/> |
|Conexão de novo usuário  <br/> |O usuário pode se conectar no pool de hospedagem no modo Resiliência.  <br/> |O usuário pode se conectar no pool de hospedagem original no modo normal.  <br/> |
|Conferências em andamento organizadas pelo usuário afetado  <br/> |Todas as modalidades de conferência são concluídas. O botão Reingressar aparecerá, mas nenhum usuário pode reingressar enquanto o usuário afetado está no modo Resiliência.  <br/> |Todas as modalidade funcionam agora. Cada participante precisa clicar para reingressar na conferência.  <br/> |
|Conferências em andamento organizadas pelo usuário não afetado  <br/> |A conferência continua e o usuário afetado pode permanecer na conferência. O usuário afetado está restrito ao que ele/ela pode executar no modo Resiliência.  <br/> |A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam depois que o usuário sair do modo Resiliência.  <br/> |
|Agendando ou modificando reuniões programadas, criando conferências ad-hoc  <br/> |Não é possível enquanto o usuário está no modo Resiliência.  <br/> |Disponível para todas as modalidades.  <br/> |
|Presença como vista por outros usuários no mesmo pool  <br/> |Presença desconhecida enquanto o usuário está conectado ao pool de backup durante o modo Resiliência.  <br/> |Mostra o último estado de presença definido pelo usuário e as alterações de presença serão refletidas a partir de agora.  <br/> |
|Disponibilidade da lista de contatos e do serviço de Catálogo de endereços  <br/> |Não disponível  <br/> |Disponível  <br/> |
|Todas as sessões e modalidades ponto a ponto  <br/> |Disponível  <br/> |Disponível  <br/> |
   
**Experiência do usuário para um usuário hospedado em um pool não afetado durante o failback de outro pool**

|**Tarefa do usuário**|**Durante o failback**|**Depois da conclusão do failback**|
|:-----|:-----|:-----|
|Exibindo a presença do usuário afetado  <br/> |Mostra o último estado de presença definido pelo usuário afetado.  <br/> |Trabalhando. Os usuário não afetados visualizam atualizações efetuadas pelos usuário afetados.  <br/> |
|Conferências em andamento organizadas pelo usuário afetado  <br/> |Todas as modalidade de conferência são concluídas.  <br/> |Todas as modalidade funcionam agora. Cada participante precisa clicar para reingressar na conferência.  <br/> |
|Conferências em andamento organizadas pelo usuário não afetado  <br/> |A conferência continua e o usuário afetado pode continuar na conferência, com todas as modalidades funcionando.  <br/> |A conferência continua e o usuário afetado pode continuar na conferência, com todas as modalidades funcionando.  <br/> |
|Todas as sessões e modalidades ponto a ponto  <br/> |Disponível  <br/> |Disponível  <br/> |
   

