---
title: 'Lync Server 2013: práticas recomendadas para a sua infraestrutura principal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c6a8663bfae2411926fe08a497a5004def051ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Práticas recomendadas para a sua infraestrutura principal no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-01-27_

Provavelmente, você já executou etapas para projetar a tolerância a falhas em seu sistema, usando práticas como assegurar a redundância de hardware, proteger contra falta de energia, instalar rotineiramente atualizações de segurança e medidas antivírus e atividade do Monitoring Server. Essas práticas se beneficiam não só na infra-estrutura do Microsoft Lync Server 2013, mas também em toda a sua rede. Se você não implementou essas práticas, recomendamos que faça isso antes de implantar o Lync Server 2013.

Para ajudar a proteger os servidores em sua implantação do Lync Server 2013 contra danos acidentais ou intencionais que podem resultar em tempo de inatividade, tome as seguintes precauções:

  - Mantenha os servidores atualizados com atualizações de segurança. A assinatura do Microsoft Security Notification Service ajuda a garantir que você receba notificações imediatas de versões de boletim de segurança de qualquer produto da Microsoft. Para se inscrever, acesse o site de notificações técnicas [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)de segurança da Microsoft em.

  - Verifique se os direitos de acesso estão configurados corretamente.

  - Mantenha os servidores em um ambiente físico que impeça o acesso não autorizado. Verifique se o software antivírus adequado está instalado em todos os servidores. Mantenha o software atualizado com os arquivos de assinatura de vírus mais recentes. Use o recurso de atualização automática do seu aplicativo antivírus para manter as assinaturas de vírus atuais.

  - Recomendamos que você desabilite os serviços do sistema operacional Windows Server que não são necessários nos computadores em que você instalou o Lync Server 2013.

  - Criptografe os sistemas operacionais e as unidades de disco em que os dados estiverem armazenados com um sistema de criptografia de volume completo, a menos que você possa garantir o controle constante e completo dos servidores, o isolamento típico total e o descomissionamento apropriado e seguro de unidades de disco substituídas ou com falha.

  - Desabilite todas as portas de DMA (Acesso Remoto Direto à Memória) externas do servido, a menos que você possa garantir o controle muito rigoroso sobre o acesso físico aos servidores. Ataques baseados em DMA, que podem ser iniciados de modo razoavelmente fácil, podem expor informações confidenciais, como chaves de criptografia privada.

</div>

<span> </span>

</div>

</div>

</div>

