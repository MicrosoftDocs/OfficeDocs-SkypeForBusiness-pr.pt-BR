---
title: Perguntas frequentes sobre a ferramenta de stress e desempenho do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Perguntas frequentes (FAQ) do Skype for Business 2015-perguntas frequentes (FAQ), útil para descobrir quais configurações da ferramenta são suportadas, problemas da ferramenta de solução de problemas e esclarecimento de comportamentos que podem ser exibidos ao executar as ferramentas de stress e desempenho .
ms.openlocfilehash: 2847ecd54389f64d6961cc72ecb94d87e847b0b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816180"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Perguntas frequentes sobre a ferramenta de stress e desempenho do Skype for Business Server 2015
 
Perguntas frequentes (FAQ) do Skype for Business 2015-perguntas frequentes (FAQ), útil para descobrir quais configurações da ferramenta são suportadas, problemas da ferramenta de solução de problemas e esclarecimento de comportamentos que podem ser exibidos ao executar as ferramentas de stress e desempenho .
  
 Estas perguntas frequentes abordam algumas das perguntas mais frequentes sobre a ferramenta de stress e desempenho do Skype for Business Server 2015 e podem ajudar na solução de problemas e opções de configuração da ferramenta.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>É possível executar o LyncPerfTool. exe na produção?

Isso **não** é recomendado. A ferramenta afeta o desempenho do servidor de produção, a segurança e a experiência do usuário final.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Estou conectando meus usuários pela primeira vez. Por que meus servidores estão executando um alto nível de carga?

Na primeira vez que os usuários fazem logon, as operações adicionais ocorrem em segundo plano. Como resultado, o desempenho no servidor back-end do Microsoft SQL Server pode ser degradado. É recomendável que você execute um teste curto que Registre todos os seus usuários e, em seguida, reinicie os clientes antes de começar a medir os resultados com a ferramenta. O Skype for Business Server não oferece suporte a mais de 12 sessões de logon do usuário simultâneas por segundo, mas lembre-se de que o número real que pode ser tratado pelos seus servidores depende da configuração do seu hardware e pode ser menor do que o valor com suporte.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Meus clientes estão ficando sem memória! O que devo fazer?

Se os clientes estiverem ficando sem memória, reduza o número de usuários conectados por pool de front-end do Skype for Business Server. Você também pode optar por dimensionar pools front-ends se o problema for persistente.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>É possível executar essa ferramenta em um servidor do Skype for Business?

Você não deve fazer isso. Não há suporte para esse cenário porque ele pode falhar devido a uma incompatibilidade binária, e também porque o objetivo é medir o consumo de recursos no servidor. Na verdade, executar a ferramenta afetaria o desempenho do servidor e invalidaria seus dados e medidas.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>É possível executar o LyncPerfTool. exe em um servidor virtual ou no Microsoft Hyper-V Server 2008/2012?

Sim, você pode.
  
## <a name="what-does-mpop-mean"></a>O que significa MPOP?

MPOP é uma maneira reduzida de dizer "vários pontos de presença". MPOP é destinado a simular cenários em que os usuários estão conectados ao cliente Skype for Business 2015 de várias máquinas ou dispositivos. Lembre-se de que, no LyncPerfTool. exe, cada ponto de extremidade usa o perfil padrão. Em outras palavras, o perfil não é dividido entre dois pontos de presença.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Comecei LyncPerfTool. exe, mas nada está acontecendo. O que está acontecendo?

Verifique o contador total de pontos de extremidade ativos nos servidores para ver se os usuários estão se conectando. Se os usuários não se conectam, verifique a configuração do Skype for Business Server 2015. O problema que você está vendo geralmente ocorre porque um dos nomes de servidor, prefixo de usuário ou senha está incorreto. Observe que os clientes externos devem especificar valores de proxy e TargetServer de acesso. Verifique o número da porta no arquivo de configuração.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Como posso ter certeza de que algo está sendo avaliado?

Há LyncPerfTool contadores de desempenho que indicam se os usuários estão se conectando e executando ações, mas a maneira mais fácil de garantir que as ações estejam sendo medidas seja fazer logon em uma das contas com um cliente do Skype for Business 2015 e fazer isso ações por conta própria. Verifique os resultados para confirmar que as medições foram tiradas.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Tenho ferramentas de planejamento de capacidade do Lync Server 2010 e/ou ferramentas de planejamento de capacidade do Lync Server 2013 instaladas. Isso é bem?

 Essas ferramentas têm problemas de interoperabilidade! Você deve desinstalar todas as versões anteriores dessas ferramentas para obter dados válidos da ferramenta de stress e desempenho do Skype for Business Server 2015.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>As ferramentas de stress e desempenho configuram a CAA Call Information Server Topology?

Não, as ferramentas não fazem isso. As ferramentas apenas criam usuários, contatos e listas de distribuição para simular a carga do usuário.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Qual é o número máximo de usuários com suporte para as ferramentas?

Em testes, criamos até um total de 80.000 usuários e executamos testes totalizando 30.000 usuários que executam essas ferramentas. Sugerimos um máximo de 120.000 usuários, embora as limitações técnicas permitam um valor mais alto. Lembre-se de que esses valores dependem do servidor e do hardware em seu ambiente.
  

