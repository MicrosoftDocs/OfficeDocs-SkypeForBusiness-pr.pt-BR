---
title: 'Lync Server 2013: verificar o design da topologia'
description: 'Lync Server 2013: Verifique o design de topologia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb1e65343aacddbc11d3b909dfdff715503cab93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560187"
---
# <a name="verify-the-topology-design-in-lync-server-2013"></a>Verificar o design de topologia no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-01-02_

O construtor de topologia verifica automaticamente a topologia. Qualquer erro na topologia é identificado como um erro de validação, indicado pelo ícone de erro de validação ao lado da função de servidor. É importante também verificar se a topologia representa de forma correta a topologia da sua implantação.

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>Para verificar a topologia antes de publicação

1.  Verifique se todas as URLs simples estão configuradas corretamente.

2.  Confirme se o servidor baseado em SQL Server está online e disponível para o computador onde o construtor de topologias está instalado, incluindo as regras de firewall necessárias.

3.  Confirme se o compartilhamento de arquivos está disponível e tem as permissões adequadas definidas.

4.  Confirme se as funções de servidor corretas que atendem aos requisitos de implantação estão definidas na topologia.

5.  Verifique se os servidores existem nos serviços de domínio do Active Directory. Isso acontecerá automaticamente se você tiver ingressado os servidores no domínio.

Após a verificação da topologia e se não houver erros de validação, você deverá estar pronto para publicar a topologia. Se houver erros de validação, será necessário corrigi-los antes de publicar a topologia. Para obter detalhes sobre como publicar sua topologia, consulte [publish the Topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

