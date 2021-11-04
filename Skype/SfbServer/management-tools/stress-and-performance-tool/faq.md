---
title: Perguntas frequentes sobre Skype for Business Server ferramenta de desempenho e estresse de 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype for Business 2015 Stress and Performance Tool perguntas frequentes (Perguntas frequentes), úteis para descobrir quais configurações de ferramentas são suportadas, solucionar problemas da ferramenta e esclarecer comportamentos que você pode ver ao executar as ferramentas stress e performance.
ms.openlocfilehash: 7a922293b4e8b938d6ed9c1d3f763a47b70a5c6c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771937"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Perguntas frequentes sobre Skype for Business Server ferramenta de desempenho e estresse de 2015
 
Skype for Business 2015 Stress and Performance Tool perguntas frequentes (Perguntas frequentes), úteis para descobrir quais configurações de ferramentas são suportadas, solucionar problemas da ferramenta e esclarecer comportamentos que você pode ver ao executar as ferramentas stress e performance.
  
 Essa perguntas frequentes aborda algumas das perguntas mais frequentes sobre a ferramenta Skype for Business Server stress e desempenho do Skype for Business Server 2015 e pode ajudar na solução de problemas e nas opções de configuração da ferramenta.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>Posso executar LyncPerfTool.exe em produção?

Isso não **é** recomendado. A ferramenta afetaria o desempenho do servidor de produção, a segurança e a experiência do usuário final.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Estou registrando meus usuários pela primeira vez. Por que meus servidores estão executando uma carga alta?

Na primeira vez que os usuários fizerem logoff, operações adicionais ocorrerão em segundo plano. Como resultado, o desempenho no servidor Microsoft SQL Server back-end pode ser degradado. É recomendável que você execute um teste curto que registra todos os usuários e reinicie os clientes antes de começar a medir os resultados com a ferramenta. Skype for Business Server não oferece suporte a mais de 12 sessões de logon de usuário simultâneas por segundo, mas lembre-se de que o número real que pode ser manipulado por seus servidores depende da configuração de hardware e pode ser menor do que o valor suportado.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Meus clientes estão ficando sem memória! O que devo fazer?

Se os clientes estão ficando sem memória, você deve reduzir o número de usuários conectados por Skype for Business Server pool de Front-End. Você também pode optar por dimensionar pools de Front-End se o problema for persistente.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>Posso executar essa ferramenta em um servidor Skype for Business, em si mesmo?

Você não deve fazer isso. Esse cenário não é suportado porque pode falhar devido a uma incompatibilidade binária e também porque o objetivo é medir o consumo de recursos no servidor. Na verdade, a execução da ferramenta afetaria o desempenho do servidor e invalidaria seus dados e medidas.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Posso executar LyncPerfTool.exe em um Servidor Virtual ou no Microsoft Hyper-V Server 2008/2012?

Sim, você pode.
  
## <a name="what-does-mpop-mean"></a>O que significa MPOP?

MPOP é uma maneira abreviada de dizer "vários pontos de presença". O MPOP deve simular cenários em que os usuários estão conectados Skype for Business cliente 2015 de vários dispositivos ou máquinas. Saiba que, em LyncPerfTool.exe, cada ponto de extremidade usa o perfil padrão. Em outras palavras, o perfil não é dividido entre dois pontos de presença.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Eu LyncPerfTool.exe mas nada está acontecendo. O que está acontecendo?

Verifique o contador Total de Pontos de Extremidade Ativos nos servidores para ver se os usuários estão se conectando. Se os usuários não estão se conectando, verifique sua configuração Skype for Business Server 2015. O problema que você está vendo geralmente ocorre porque um dos nomes de servidor, prefixo de usuário ou senha está incorreto. Observe que clientes externos devem especificar valores de Proxy de Acesso e TargetServer. Verifique o número da porta no arquivo de configuração.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Como posso ter certeza de que algo está sendo medido?

Existem contadores de desempenho do LyncPerfTool que indicam se os usuários estão ou não se conectando e executando ações, mas a maneira mais fácil de garantir que as ações estão sendo medidas é fazer logon em uma das contas com um cliente do Skype for Business 2015 e fazer essas ações por conta própria. Verifique os resultados para confirmar se as medidas foram tomadas.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Tenho as Ferramentas de Planejamento de Capacidade do Lync Server 2010 e/ou Lync Server 2013 instaladas. Está tudo bem?

 Essas ferramentas têm problemas de interoperabilidade! Você deve desinstalar todas as versões anteriores dessas ferramentas para obter dados válidos da ferramenta Skype for Business Server Stress and Performance 2015.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>As ferramentas de Estresse e Desempenho configurarão a topologia do servidor de Informações de Chamada da CAA?

Não, as ferramentas não fazem isso. As ferramentas criam apenas usuários, contatos e listas de distribuição para simular a carga do usuário.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Qual é o número máximo de usuários que as ferramentas suportam?

Em testes, criamos até um total de 80.000 usuários e executamos testes que totalizam 30.000 usuários executando essas ferramentas. Sugerimos um máximo de 120.000 usuários, embora as limitações técnicas permitam valores mais altos. Lembre-se de que esses valores dependem do servidor e do hardware em seu ambiente.
  

