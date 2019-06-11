---
title: 'Lync Server 2013: visão geral do monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88bfb8170b2334c322c612628daa1f8b9db2473c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a>Visão geral do monitoramento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-05_

No Microsoft Lync Server 2013, o monitoramento é usado para coletar dados de uso e dados de qualidade da experiência (QoE) sobre as sessões de comunicação nas quais seus usuários participam. Uma sessão é um termo genérico que abrange a conexão de um usuário a:

  - Conferência

  - Modalidade de conferência (como áudio/vídeo ou compartilhamento de aplicativos)

  - um outro usuário em uma conversa ponto a ponto, como mensagens instantâneas ou uma chamada de áudio

<div>


> [!NOTE]  
> O Lync Server 2013 controla as informações sobre cada sessão: quem chamou quem; quais pontos de extremidade foram usados na sessão; Qual foi a duração da sessão por último; Qual foi a qualidade percebida da sessão; e assim por diante. No entanto, o Lync Server não grava e armazena a chamada propriamente dita. Isso também inclui sessões de mensagens instantâneas: embora o Lync Server Registre informações sobre sessões de mensagens instantâneas, ele não mantém um registro de cada mensagem instantânea enviada durante a sessão.



</div>

As informações de detalhes de chamadas coletadas pelo Lync Server podem ser empregadas para qualquer número de usos, incluindo:

  - **Retorno sobre o investimento (ROI)**. Os administradores podem comparar os dados de uso coletados pelo Monitoring Server com dados similares coletados para o sistema de telefonia anterior a fim de mostrar a redução de custos e ajudar a justificar a implantação do Lync Server.

  - **Gerenciamento de estoque de dispositivos**. As informações de gerenciamento de ativos ajudam os administradores a identificar dispositivos antigos que ainda estão em uso que precisam ser substituídos, além de identificar dispositivos caros que não parecem estar sendo usados.

  - Suporte técnico. A solução de problemas de dados permite aos engenheiros de suporte determinar por que a chamada de um usuário falhou e fazer isso sem precisar coletar os logs do lado do servidor ou do cliente. Essas informações podem ser acessadas de forma imediata e compreendidas pela equipe de suporte que não tenha conhecimento técnico profundo do Microsoft Lync 2013 e do Lync Server 2013.

  - **Solução de problemas de sistemas**. Habilita os administradores a detectar problemas graves que podem impedir os usuários de executar tarefas básicas, como ingressar em uma conferência, estabelecer uma chamada ou enviar uma mensagem instantânea.

Além dessas informações básicas de chamadas, o Monitoring Server também fornece um mecanismo que permite que pontos de extremidade SIP (como o Lync 2013) forneçam informações de solução de problemas que o servidor não teria, de outra forma, ter acesso a:

  - **Métricas de mídia que influenciam a qualidade**. Essas métricas lidam com a transmissão real da chamada em si; ou seja, eles fornecem um tipo de registro de viagens como viagem de chamadas pela rede. Essas métricas (que incluem itens como perda de pacotes, tremulação e tempos de viagem de ida e volta) fornecem informações sobre o que aconteceu com a chamada no momento em que ele saiu do ponto de extremidade até o momento em que chegou ao ponto de extremidade da outra pessoa.

  - **Problemas comunicados ao usuário final**. Essas métricas incluem notificações de baixa qualidade que o Lync 2013 apresenta aos usuários finais em casos onde eles estão longe de um microfone, falando muito sem problemas, com uma conexão de rede ruim ou com baixa qualidade porque outro programa no computador é consumindo os recursos disponíveis.

  - **Informações sobre o ambiente**. Essas métricas detalham fatores de qualidade das chamadas, como tipo de microfone e alto-falantes usados e se o usuário está conectado através de uma VPN ou de uma rede sem fio.

No final de cada chamada, os pontos de extremidade compatíveis com SIP transmitem essas informações automaticamente para o servidor front-end que facilitou a chamada. Não é necessária nenhuma ação para que os pontos de extremidade transmitam essas informações, pois esse comportamento já está incorporado ao protocolo SIP. No entanto, se desejar coletar e armazenar essas informações, você precisará instalar e habilitar o monitoramento. Se fizer isso, as informações das chamadas serão coletadas pelos agentes em execução no Servidor Front-End e transmitidas para um par de bancos de dados do SQL Server.

Observe que o processo de instalação e configuração do monitoramento foi simplificado no Lync Server 2013. Em versões anteriores do software, o monitoramento exigia uma função de servidor de monitoramento separada, que normalmente significa que um computador separado reservava para uso como o servidor de monitoramento. No Lync Server 2013, no entanto, a função de servidor de monitoramento foi eliminada. Em vez disso, o serviço de monitoramento (na forma de "agentes da coleta de dados unificados") foi posicionado em todos os servidores de front-end. Isso tem pelo menos dois benefícios importantes. Colocação do serviço de monitoramento:

  - Diminui o número de funções de servidor necessárias ao implementar o Lync Server 2013. Decrementar a função de servidor de monitoramento também ajuda a reduzir os custos, eliminando a necessidade de manter servidores dedicados para monitoramento.

  - Reduz a complexidade da configuração e administração do Lync Server 2013. Posicionando os serviços de monitoramento em cada servidor front-end que você não precisa mais instalar, configurar e gerenciar a função do servidor de monitoramento.

Para obter mais informações, consulte o tópico implantando o [monitoramento no Lync server 2013](lync-server-2013-deploying-monitoring.md) no guia de implantação do lync Server 2013 2013.

</div>

<span> </span>

</div>

</div>

</div>

