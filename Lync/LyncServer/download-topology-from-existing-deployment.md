---
title: Baixar topologia da implantação existente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29a8bd95af99b6b79b91f84231120c6981eeedb7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a>Baixar topologia da implantação existente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-29_

Ao criar um pool do Lync Server 2013, você usará o repositório de gerenciamento central associado ao Lync Server 2010. Ao iniciar o construtor de topologia na primeira utilização e em sessões de edição subsequentes, você será solicitado a fornecer o local onde deseja que o construtor de topologias carregue o documento de configuração atual. Como você já tem uma topologia do Lync Server 2010 definida e estabeleceu o repositório de gerenciamento central, você deve optar por baixar uma topologia de uma implantação existente. O construtor de topologias lerá o banco de dados e recuperará a definição atual.

**Para baixar uma topologia de uma implantação existente**

1.  Abra o **Assistente de implantação do Lync Server**.

2.  Na página **Lync Server 2013 – assistente de implantação** , clique em **instalar ferramentas administrativas**.

3.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013** e, em seguida, clique em **Construtor de topologias do Lync Server**.

4.  Selecione **baixar a topologia na implantação existente**.
    
    ![Configurações do construtor de topologia do assistente de implantação](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Configurações do construtor de topologia do assistente de implantação")

5.  Escolha um nome de arquivo e salve a topologia com o tipo de arquivo default. tbxml.

6.  Expanda o nó do Lync Server, como mostrado, para revelar as várias funções de servidor na implantação.
    
    ![Propriedades gerais da função de servidor do construtor de topologia](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Propriedades gerais da função de servidor do construtor de topologia")

</div>

<span> </span>

</div>

</div>

</div>

