---
title: 'Lync Server 2013: verificando o uso do disco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55d8881bc8b8a55351cc088c230574b958718a63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a>Verificar o uso do disco no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-04-30_

Unidades de discos rígidos são um componente importante da implantação do Lync Server 2013. Sem um volume de disco livre suficiente, nem os bancos de dados do sistema operacional nem do Lync Server 2013 podem funcionar corretamente. Você deve monitorar as estatísticas de banco de dados de back-end do Lync Server 2013 diariamente para ajudar a garantir que os servidores não fique sem espaço em disco e para se preparar para adicionar recursos de armazenamento conforme necessário.

Além de verificar o espaço em discos que hospedam o sistema operacional, arquivos de programas, bancos de dados e logs de transações (Lync Server 2013 back-end), você também deve monitorar o uso do sistema de arquivos que inclui o espaço em disco para compartilhamentos de arquivos que contenham as seguintes importantes os

  - Conteúdo de reunião

  - Metadados de conteúdo da reunião

  - Cumprir logs de conformidade

  - Arquivos de dados de aplicativo (usados internamente pelo componente de servidor de aplicativos)

  - Serviço Web de servidor de chat de grupo e pastas de conformidade (para armazenar arquivos carregados no serviço Web de chat de grupo)

  - Arquivos XML de conformidade de chat de grupo (que contêm registros de conformidade de chat de grupo)

  - Atualizar arquivos (para o serviço de atualização de dispositivo)

  - Arquivos de Catálogo de endereços

O Lync Server 2013 precisa de espaço em disco rígido para armazenar seus bancos de dados e logs de transações, além de arquivos em compartilhamentos de arquivos listados anteriormente.

Você deve monitorar o espaço em disco regularmente para ajudar a garantir que a implantação do Lync Server 2013 não seja prejudicada devido a recursos de armazenamento insuficientes.

Comparar e manter informações estatísticas sobre o espaço em disco disponível em cada volume do Lync Server 2013 e o crescimento esperado dos arquivos de log de transações e bancos de dados. Isso ajuda no planejamento da capacidade e na adição de armazenamento quando os recursos de armazenamento são necessários.

Para acomodar as situações de solução de problemas e recuperação de desastre, recomendamos que o espaço disponível no volume seja igual ou maior que 110 por cento do tamanho do banco de dados.

Você pode verificar o espaço em disco usando os métodos a seguir:

1.  **O System Center Operations Manager**   System Center Operations Manager pode ser usado para avisar aos administradores quando o espaço do volume é restrito.

2.  **Executar um script**   monitor Disk Space executando um script que envia uma mensagem se o espaço disponível no disco rígido estiver abaixo de 20 por cento. Você pode encontrar um script de exemplo no Microsoft Script Center no TechNet, examinar:[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **O Windows Explorer**   usa o Windows Explorer para verificar o espaço em disco em volumes que armazenam logs e bancos de dados do Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

