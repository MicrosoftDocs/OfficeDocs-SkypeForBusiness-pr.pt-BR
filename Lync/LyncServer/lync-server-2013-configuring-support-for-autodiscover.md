---
title: 'Lync Server 2013: Configurando o suporte para descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee85d984f0d60d4275972982e4ff65b380f0f9b2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Configurando o suporte para descoberta automática no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-21_

O **serviço de descoberta automática** de serviços Web do Lync Server apareceu pela primeira vez na atualização cumulativa do lync Server 2010: novembro de 2011. Esta atualização foi acompanhada pela versão inicial dos clientes móveis do Lync. O serviço de descoberta automática expôs os serviços de mobilidade, conhecidos como o serviço MCX.

O serviço de descoberta automática atua como um único local para que todos os clientes solicitem informações sobre quais serviços e recursos estão disponíveis e como entrar em contato com o sevices – por meio de um nome de domínio totalmente qualificado ou uma referência de localizador de recursos uniforme da Web. A descoberta automática expõe vários recursos, e cada cliente fará solicitações com base nos recursos que o cliente pode usar. Por exemplo, um cliente do Lync 2013 da área de trabalho usará o autodiscvoer para determinar os serviços Web externos, mas não usará os serviços de mobilidade (MCX). Para definir e habilitar corretamente seus clientes para usar os recursos disponíveis para eles, os cenários que permitem que um cliente encontre e use as entradas de descoberta automática devem ser definidos. Para usar o autodoscover, sua implantação requer que um proxy reverso publique os serviços Web do Lync Server, que os registros DNS estão configurados para resolver consultas de DNS para o serviço de descoberta automática do Lync Server e serviços Web do Lync Server e que os serviços de certificados estão configurados corretamente para o seu cenário específico.

<div>


> [!TIP]  
> Para obter detalhes técnicos sobre o que os elementos da solicitação/resposta de descoberta automática fazem, consulte <A href="lync-server-2013-understanding-autodiscover.md">Understanding autodiscover in Lync Server 2013</A>.



</div>

As informações e tabelas a seguir definem, por cenário, quais configurações (se houver) que você precisa implementar para fornecer o uso completo e efetivo do serviço de descoberta automática. As informações nos tópicos a seguir são específicas para o Microsoft Lync Server 2013. Se você estiver procurando orientações sobre como planejar a mobilidade para o Lync Server 2010, consulte [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113). Para implantar a mobilidade para o Lync Server 2010, consulte[https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurando o DNS para descoberta automática no Lync Server 2013](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Configurando certificados para descoberta automática no Lync Server 2013](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Configurando um proxy reverso para descoberta automática no Lync Server 2013](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Configurando a descoberta automática no Lync Server 2013 para implantações híbridas](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

