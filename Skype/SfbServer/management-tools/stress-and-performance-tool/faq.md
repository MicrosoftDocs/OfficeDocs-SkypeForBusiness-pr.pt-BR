---
title: Perguntas frequentes para o Skype para Business Server 2015 ferramenta de Stress e desempenho
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype para negócios 2015 ferramenta de Stress e desempenho perguntas frequentes (FAQ), útil para descobrir quais configurações da ferramenta são suportadas, solução de problemas de ferramenta e esclarecimento sobre behaviours, que você pode ver ao executando as ferramentas de Stress e desempenho .
ms.openlocfilehash: 604644d5aecb12f94304d1c7ce271c68208e1964
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906743"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Perguntas frequentes para o Skype para Business Server 2015 ferramenta de Stress e desempenho
 
Skype para negócios 2015 ferramenta de Stress e desempenho perguntas frequentes (FAQ), útil para descobrir quais configurações da ferramenta são suportadas, solução de problemas de ferramenta e esclarecimento sobre behaviours, que você pode ver ao executando as ferramentas de Stress e desempenho .
  
 Estas perguntas frequentes aborda algumas das perguntas mais frequentes sobre o Skype para ferramenta Business Server 2015 Stress e desempenho e podem ajudar com as opções de configuração de solução de problemas e a ferramenta.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>Podem executar LyncPerfTool.exe em produção?

Isso **não** é recomendado. A ferramenta afetaria o desempenho do servidor de produção, segurança e a experiência do usuário final.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Eu estou logon meus usuários pela primeira vez. Por que meus servidores estão executando uma carga elevada?

Na primeira vez em que os usuários efetuam logon, operações adicionais ocorrerem em segundo plano. Como resultado, o desempenho em que o Microsoft SQL Server servidor Back-End pode ser degradado. É recomendável que você executa um teste curto que faça logon em todos os seus usuários e, em seguida, reiniciar os clientes antes de começar a medir os resultados com a ferramenta. Skype para Business Server não suporta mais de 12 sessões de logon de usuário simultâneas por segundo, mas esteja ciente o número real que pode ser manipulado pelos servidores depende da configuração de hardware e pode ser menor que o valor com suporte.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Meus clientes estão ficando sem memória! O que deve fazer?

Se os clientes estão ficando sem memória, você deve reduzir o número de usuários conectados por Skype para pool de Front End do servidor de negócios. Você também pode optar por dimensionar frontal pools final se o problema é persistente.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>Posso executar essa ferramenta em um Skype para Business server, em si?

Você não deve fazer isso. Esse cenário não é suportado porque ele pode falhar devido a uma incompatibilidade de binária e também porque o objetivo é para medir o consumo de recursos no servidor. Na verdade, executando a ferramenta lá, seria impactar o desempenho do servidor e invalidar seus dados e medidas.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Posso executar LyncPerfTool.exe em um servidor Virtual ou no Microsoft Hyper-V Server 2008/2012?

Sim, você pode.
  
## <a name="what-does-mpop-mean"></a>O que significa MPOP?

MPOP é uma forma abreviada do dizendo "vários pontos de presença". MPOP destina-se para simular cenários onde usuários esteja conectados ao Skype para negócios 2015 client a partir de vários computadores ou dispositivos. Lembre-se de que, em LyncPerfTool.exe, cada ponto de extremidade usa o perfil padrão. Em outras palavras, o perfil não é dividido entre dois pontos de presença.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Comecei LyncPerfTool.exe mas nada acontece. O que está acontecendo?

Verifique o contador de pontos de extremidade ativos Total nos servidores para ver se os usuários estão se conectando. Se os usuários não estejam se conectando, verifique se seu Skype para configuração de negócios Server 2015. O problema que você está vendo geralmente ocorre porque um dos nome do servidor, o prefixo de usuário ou senha, está incorreto. Tome nota que os clientes externos devem especificar os valores de Proxy de acesso e o servidor de destino. Verifique se o número da porta no arquivo de configuração.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Como posso ter certeza de que algo está sendo medido?

Existem LyncPerfTool contadores de desempenho que indicam se os usuários estão conectando e ações de desempenho, mas é a maneira mais fácil para certificar-se de ações que estão sendo medidas faça logon em uma das contas com um Skype para negócios 2015 cliente e fazer isso ações sozinho. Verifique os resultados para confirmar as medidas feitos.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Posso ter as ferramentas de ferramentas de planejamento de capacidade do Lync Server 2010 e/ou o planejamento de capacidade do Lync Server 2013 instaladas. É isto okey?

 Essas ferramentas têm problemas de interoperabilidade! Você deve desinstalar todas as versões anteriores da ferramenta de desempenho e essas ferramentas obter dados válidos a partir do Skype para 2015 carga do servidor de negócios.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>As ferramentas de Stress e desempenho irá configurar a topologia de servidor de informações de chamada CAA?

Não, as ferramentas não fazem isso. As ferramentas só criam usuários, contatos e listas de distribuição, para simular a carga de usuários.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>O que é o número máximo de usuários que as ferramentas de suportam?

Em testes, podemos ter criado em um total de 80.000 usuários e executado testes totalizando 30.000 usuários executando essas ferramentas. Sugerimos um máximo de 120.000 usuários, embora as limitações técnicas permitem um valores mais altos. Lembre-se de que esses valores dependem do servidor e o hardware no seu ambiente.
  

