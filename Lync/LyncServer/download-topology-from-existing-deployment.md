---
title: Baixar a topologia da implantação existente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19cf24e1ef287b50ffece7407913a7d2c45e7062
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a>Baixar a topologia da implantação existente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-29_

Ao criar um pool do Lync Server 2013, você usará o repositório de gerenciamento central associado ao Lync Server 2010. Quando você iniciar o construtor de topologia no primeiro uso e nas sessões de edição subsequentes, será solicitado o local em que deseja que o construtor de topologia carregue o documento de configuração atual. Como você já tem uma topologia do Lync Server 2010 definida e estabeleceu o repositório de gerenciamento central, você deve optar por baixar uma topologia de uma implantação existente. O construtor de topologias lerá o banco de dados e recuperará a definição atual.

**Para baixar uma topologia de uma implantação existente**

1.  Abra o **Assistente de implantação do Lync Server**.

2.  No **Lync Server 2013 – página Assistente de implantação** , clique em **instalar ferramentas administrativas**.

3.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013** e em **Construtor de topologias do Lync Server**.

4.  Selecione **Download da topologia de uma implantação existente**.
    
    ![Configurações do construtor de topologia do assistente de implantação](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Configurações do construtor de topologia do assistente de implantação")

5.  Escolha um nome de arquivo e salve a topologia com um tipo de arquivo padrão .tbxml.

6.  Expanda o nó do Lync Server, conforme mostrado, para revelar as várias funções de servidor na implantação.
    
    ![Propriedades gerais da função de servidor do construtor de topologia](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Propriedades gerais da função de servidor do construtor de topologia")

</div>

<span> </span>

</div>

</div>

</div>

