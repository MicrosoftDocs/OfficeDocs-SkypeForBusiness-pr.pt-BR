---
title: Remover BackCompatSite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6a3d1dc92e45bc99892e7827394376b6f28b12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a>Remover BackCompatSite

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Após a desativação de todos os pools e a desinstalação de todos os servidores de borda, execute o assistente de mesclagem do construtor de topologias para remover o **BackCompatSite**.

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>Para remover o site de adcompatibilidade do construtor de topologias

1.  Abrir uma implantação existente do construtor de topologias.

2.  No menu **ação** , clique em **Merge 2007 R2 Topology**.

3.  Clique em **Avançar** para continuar.

4.  Na página **especificar borda herdada** , certifique-se de que a lista de servidores de borda está vazia. Se a lista não estiver vazia, use o botão **remover** para remover todos os servidores de borda herdados e clique em **Avançar**.
    
    ![Assistente de topologia de mesclagem, especificar a página de configuração de borda] (images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Assistente de topologia de mesclagem, especificar a página de configuração de borda")  

5.  Na página **especificar a configuração da porta SIP interna** , clique em **Avançar**.

6.  Na página **Resumo** , clique em **Avançar** para começar a mesclar as topologias e remover o site herdado.

7.  Na coluna **status** , verifique se o valor é **êxito** e clique em **concluir** para fechar o assistente.

8.  No painel esquerdo do construtor de topologias, expanda o BackCompatSite e assegure-se de que nenhum servidor esteja listado.

9.  Clique com o botão direito do mouse no **BackCompatSite**e, em seguida, clique em **excluir**.

10. Em **Construtor de topologia**, selecione o nó mais superior do **Lync Server**.

11. No menu **ação** , selecione **publicar topologia** e clique em **Avançar**.

12. Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

