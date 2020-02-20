---
title: 'Lync Server 2013: práticas recomendadas para sua infraestrutura principal'
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
ms.openlocfilehash: 876a4de1357786e2d5089fdc632002107a6c7cc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Práticas recomendadas para sua infraestrutura principal no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-01-27_

Provavelmente, você já executou etapas para designar a tolerância a falha em seu sistema, usando práticas como a garantia da redundância de hardware, proteção contra perda de energia, instalação rotineira de atualizações de segurança e medidas antivírus, e atividade do Monitoring Server. Essas práticas se beneficiam não apenas da infraestrutura do Microsoft Lync Server 2013, mas também de toda a sua rede. Se você não tiver implementado essas práticas, recomendamos fazê-lo antes de implantar o Lync Server 2013.

Para ajudar a proteger os servidores em sua implantação do Lync Server 2013 de danos acidentais ou intencionais que podem resultar em tempo de inatividade, tome as seguintes precauções:

  - Mantenha em dia as atualizações de segurança nos servidores. Inscreva-se no serviço Microsoft Security Notification Service para receber uma notificação imediata do lançamento de boletins de segurança referentes a qualquer produto da Microsoft. Para se inscrever, acesse o site Microsoft Technical Security [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202)Notifications em.

  - Certifique-se de que os direitos de acesso estão configurados corretamente.

  - Mantenha os servidores em um ambiente físico que evite o acesso não autorizado. Verifique se um software antivírus adequado está instalado em todos os servidores. Mantenha o software atualizado com os arquivos de assinatura de vírus mais recentes. Use o recurso de atualização automática do aplicativo antivírus para deixar essas assinaturas sempre em dia.

  - Recomendamos que você desabilite os serviços do sistema operacional Windows Server que não são necessários nos computadores em que você instala o Lync Server 2013.

  - Criptografe os sistemas operacionais e as unidades de disco nos quais os dados são armazenados com um sistema de criptografia de volume completo, a menos que você possa garantir um controle constante e completo dos servidores, isolamento físico total e descomissionamento apropriado e seguro de unidades de disco substituídas ou com falha.

  - Desabilite todas as portas DMA (Acesso direto à memória) externas do servidor, a menos que você possa garantir um controle muito rígido sobre o acesso físico aos servidores. Os ataques baseados em DMA, que podem ser iniciados com bastante facilidade, podem expor informações muito confidenciais, como chaves de criptografia privadas.

</div>

<span> </span>

</div>

</div>

</div>

