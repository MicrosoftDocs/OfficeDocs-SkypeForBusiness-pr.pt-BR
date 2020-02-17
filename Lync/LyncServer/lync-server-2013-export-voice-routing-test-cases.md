---
title: 'Lync Server 2013: exportar casos de teste de roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47d014d9c2748a5e6479c0f86ebd32255f3361ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Exportar casos de teste de roteamento de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Os casos de teste fornecem uma maneira de testar as rotas de voz em sua organização: você define coisas como o número a ser discado e o plano de discagem e a política de voz a serem empregados e o Lync Server pode então verificar se, dadas essas condições, o número fornecido pode ser roteado com êxito para a rede PSTN.

Os casos de teste, que podem ser criados usando o painel de controle do Lync Server, são normalmente salvos somente no servidor onde o caso foi originalmente criado e executado. No entanto, esses casos de teste podem ser exportados como arquivos XML (com a extensão. vtest) e importados em outros servidores. Isso permite que você execute os mesmos testes em computadores diferentes localizados em diferentes pontos da sua topologia.

<div>

## <a name="to-export-a-voice-routing-test-case"></a>Para exportar um caso de teste de roteamento de voz

1.  No painel de controle do Lync Server, clique em **Roteamento de voz** e em **testar roteamento de voz**.

2.  Na guia **testar roteamento de voz** , selecione o caso de teste (ou casos de teste) a ser exportado. Para selecionar vários casos de teste, clique no primeiro caso a ser exportado e, em seguida, pressione a tecla CTRL e selecione os casos adicionais a serem exportados.

3.  Clique em **ação**e em **Exportar casos de teste**.

4.  Na caixa de diálogo **salvar como** , selecione uma pasta para armazenar os casos de teste exportados e digite um nome para o arquivo XML resultante na caixa **nome do arquivo** . Observe que, se você estiver exportando vários casos de testes, todos esses casos de teste serão salvos em um único arquivo XML.

5.  Para salvar os casos de teste, clique em **salvar**.

</div>

<div>

## <a name="see-also"></a>Confira Também


[Importar casos de teste de roteamento de voz no Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

