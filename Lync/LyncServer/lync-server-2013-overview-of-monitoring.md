---
title: 'Lync Server 2013: visão geral do monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66dd239acbb274c7223363f1522f2d0c76590c37
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a>Visão geral do monitoramento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-05_

No Microsoft Lync Server 2013, o monitoramento é usado para coletar informações de uso e dados de qualidade da experiência (QoE) sobre as sessões de comunicação nas quais seus usuários estão envolvidos. Sessão é um termo genérico que abrange uma conexão do usuário com:

  - Conferência

  - Uma modalidade de conferência (como áudio/vídeo ou compartilhamento de aplicativos)

  - Outro usuário em uma conversa ponto a ponto, como mensagens instantâneas ou uma chamada de áudio

<div>


> [!NOTE]  
> O Lync Server 2013 mantém controle das informações sobre cada sessão: quem chamou quem; quais pontos de extremidade foram usados na sessão; Quanto tempo foi a sessão por último; Qual era a qualidade percebida da sessão; e assim por diante. No entanto, o Lync Server não grava e armazena a chamada propriamente dita. Isso também inclui sessões de mensagens instantâneas: embora o Lync Server Registre informações sobre sessões de mensagens instantâneas, ele não mantém um registro de cada mensagem instantânea enviada durante a sessão.



</div>

As informações de detalhes da chamada coletadas pelo Lync Server podem ser empregadas para qualquer número de usos, incluindo:

  - **ROI (retorno do investimento)**. Os administradores podem comparar os dados de uso coletados pelo Monitoring Server com dados similares coletados pelo sistema de telefonia anterior para mostrar a economia de custos e ajudar a justificar a implantação do Lync Server.

  - **Gerenciamento de inventário de dispositivos**. As informações de gerenciamento de ativos ajudam os administradores a identificar dispositivos antigos ainda em uso que precisam ser substituídos, bem como dispositivos caros que podem simplesmente não estar sendo usados.

  - Assistência técnica. Dados sobre solução de problemas permitem que os engenheiros de suporte determinem o motivo da falha de uma chamada do usuário sem a necessidade de coletar logs do cliente ou do servidor. Essas informações podem ser prontamente acessadas e compreendidas pela equipe de suporte que não têm um conhecimento técnico profundo do Microsoft Lync 2013 e do Lync Server 2013.

  - **Solução de problemas de sistemas**. Permite que os administradores detectem problemas graves que podem impedir que os usuários executem tarefas básicas, como ingressar em uma conferência, estabelecer uma chamada ou enviar uma mensagem instantânea.

Além dessas informações básicas de chamada, o Monitoring Server também fornece um mecanismo que permite que os pontos de extremidade SIP (como o Lync 2013) forneçam informações de solução de problemas às quais o servidor não teria acesso:

  - **Métricas de mídia que influenciam a qualidade**. Essas métricas lidam com a transmissão da chamada propriamente dita, ou seja, elas fornecem um log de trajeto à medida que a chamada passa pela rede. Essas métricas, que incluem itens como perda de pacotes, tremulação e tempo entre saída e chegada, fornecem informações sobre o que aconteceu com a chamada do momento em que ela saiu do seu ponto de extremidade até o momento em que chegou ao ponto de extremidade do outro usuário.

  - **Problemas comunicados ao usuário final**. Essas métricas incluem notificações de baixa qualidade que o Lync 2013 apresenta aos usuários finais em casos em que eles estão muito distantes de um microfone, falando muito simples, têm uma conexão de rede ruim ou estão tendo uma qualidade ruim porque outro programa no computador é consumo dos recursos disponíveis.

  - **Informações sobre o ambiente**. Essas métricas detalham fatores de qualidade das chamadas, como tipo de microfone e alto-falantes usados e se o usuário está conectado através de uma VPN ou de uma rede sem fio.

No final de cada chamada, os pontos de extremidade compatíveis com SIP transmitem essas informações automaticamente para o servidor front-end que intermediou a chamada. Não é necessária nenhuma ação manual para que os pontos de extremidade transmitam essas informações, pois essa função já é incorporada ao protocolo SIP. No entanto, se você desejar coletar e armazenar essas informações, precisará instalar e habilitar o monitoramento. Se fizer isso, as informações sobre as chamadas serão coletadas pelos agentes em execução no servidor front-end e transmitidas para um par de bancos de dados do SQL Server.

Observe que o processo de instalação e configuração do monitoramento foi simplificado no Lync Server 2013. Em versões anteriores do software, o monitoramento exigia uma função de Servidor de Monitoramento separada, ou seja, era necessário reservar um computador separado para ser usado como o Servidor de Monitoramento. No Lync Server 2013, no entanto, a função de servidor de monitoramento foi eliminada. Em vez disso, o serviço de monitoramento (no formato de "agentes de coleta de dados unificados") foi incorporado a todos os servidores front-end. Isso traz pelo menos dois benefícios importantes. A incorporação do serviço de monitoramento:

  - Diminui o número de funções de servidor necessárias ao implementar o Lync Server 2013. A redução de função de Servidor de Monitoramento também ajuda a reduzir os custos, pois elimina a necessidade de manter servidores dedicados para monitoramento.

  - Reduz a complexidade da instalação e administração do Lync Server 2013. Ao integrar os serviços de monitoramento a cada servidor front-end, não é mais necessário instalar, configurar e gerenciar a função do Servidor de Monitoramento.

Para obter mais informações, consulte o tópico [Deploying Monitoring in Lync server 2013](lync-server-2013-deploying-monitoring.md) no lync Server 2013 2013 Deployment Guide.

</div>

<span> </span>

</div>

</div>

</div>

