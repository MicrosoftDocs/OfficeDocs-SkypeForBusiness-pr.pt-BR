---
title: 'Lync Server 2013: Verificar o design de topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe262033699e46c77897652cf48969d46b7817f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a>Verificar o design de topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-01-02_

O construtor de topologias verifica automaticamente a topologia. Qualquer erro de topologia é identificado como um erro de validação, indicado pelo ícone de erro de validação ao lado da função do servidor. Também é importante verificar se a topologia representa corretamente a topologia para a implantação.

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>Para verificar a topologia antes da publicação

1.  Verifique se todas as URLs simples estão configuradas corretamente.

2.  Verifique se o servidor baseado em SQL Server está online e disponível para o computador no qual o Construtor de Topologias está instalado, incluindo quaisquer regras de firewall necessárias.

3.  Confirme se o compartilhamento de arquivos está disponível e se tem as permissões adequadas definidas.

4.  Verifique se as funções de servidor corretas que atendem aos requisitos de implantação estão definidas na topologia.

5.  Verifique se os servidores existem nos serviços de domínio Active Directory. Isso ocorrerá automaticamente se você tiver ingressado nos servidores do domínio.

Após a verificação da topologia, se não houver erros de validação, você estará pronto para publicar a topologia. Se houver erros de validação, você deve corrigi-los para poder publicar a topologia. Para obter detalhes sobre como publicar sua topologia, consulte [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

