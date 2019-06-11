---
title: 'Lync Server 2013: Exportar casos de teste de roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e47158d9ea3da6f04a1424026c7edb73c1d482
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Exportar casos de teste de roteamento de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Os casos de teste fornecem uma maneira de testar as rotas de voz em sua organização: você define itens como o número a ser discado e o plano de discagem e a política de voz a ser empregado, e o Lync Server pode, em seguida, verificar se, dadas essas condições, o número fornecido pode foi roteada com êxito para a rede PSTN.

Os casos de teste, que podem ser criados usando o painel de controle do Lync Server, geralmente são salvos apenas no servidor em que o caso foi originalmente criado e executado. No entanto, esses casos de teste podem ser exportados como arquivos XML (com a extensão. vtest) e depois importados em outros servidores. Isso permite que você execute os mesmos testes em computadores diferentes localizados em diferentes pontos da topologia.

<div>

## <a name="to-export-a-voice-routing-test-case"></a>Para exportar um caso de teste de roteamento de voz

1.  No painel de controle do Lync Server, clique em **Roteamento de voz** e, em seguida, clique em **testar roteamento de voz**.

2.  Na guia **Roteamento de voz de teste** , selecione o caso de teste (ou casos de teste) a ser exportado. Para selecionar vários casos de teste, clique no primeiro caso para ser exportado, mantenha a tecla Ctrl pressionada e selecione os casos adicionais a serem exportados.

3.  Clique em **ação**e, em seguida, clique em **Exportar casos de teste**.

4.  Na caixa de diálogo **salvar como** , selecione uma pasta para armazenar os casos de teste exportados e digite um nome para o arquivo XML resultante na caixa **nome do arquivo** . Observe que, se você estiver exportando vários casos vários testes, todos esses casos de teste serão salvos em um único arquivo XML.

5.  Para salvar os casos de teste, clique em **salvar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Importar casos de teste de roteamento de voz no Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

