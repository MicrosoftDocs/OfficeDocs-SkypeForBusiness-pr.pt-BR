---
title: Alterar URLs simples após a migração
description: Alterar URLs simples após a migração.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f9974106d28bcfdc64c2255337baf721a937e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545757"
---
# <a name="change-simple-urls-after-migration"></a>Alterar URLs simples após a migração

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-22_

O Lync Server oferece suporte a três URLs simples:

  - **Reunir** é usado como URL base para todas as conferências no site ou na organização. Com o URL Reunir simples, os links para ingressar em reuniões são fáceis de compreender, de comunicar e distribuir.

  - **Discar** possibilita o acesso à página da web Configurações de Conferência Discada. O URL Discar é incluído em todos os convites de reuniões para que o usuário que desejar discar para ingressar na reunião possa obter acesso ao número de telefone necessário, bem como as informações do PIN.

  - O **administrador** permite acesso rápido ao painel de controle do Lync Server. A URL simples de Admin é interna à organização.

Após a migração para o Lync Server 2013, você deve estar ciente de como a alteração impacta seus registros DNS e certificados para URLs simples. Se o diretor herdado do Lync Server 2010 permanecer em uso na topologia, não será necessário fazer alterações nas suas URLs simples. Se o diretor do Lync Server 2010 for removido da topologia após a migração, os registros DNS de URL simples devem ser atualizados para apontar para um dos pools do Lync Server 2013. Contudo, sempre que você alterar o nome de um URL simples, você deve executar o Enable-CsComputer em cada servidor Diretor e Front End para registrar a alteração.

<div>

## <a name="changing-simple-urls-after-migration"></a>Alterando URLs simples após a migração

**Para atualizar a URL simples de reunião**

1.  No construtor de topologias, clique com o botão direito do mouse no nó superior **Lync Server**e clique em **Editar propriedades**.

2.  Selecione **URLs simples** no painel esquerdo e, abaixo das **URLs da reunião:** selecione a URL de reunião e clique em **Editar URL**.

3.  Atualize a URL para o valor desejado e clique em **OK** para salvar a URL editada.

**Para atualizar a URL simples de administrador**

1.  No construtor de topologias, clique com o botão direito do mouse no nó superior **Lync Server**e clique em **Editar propriedades**.

2.  Selecione **URLs simples** no painel esquerdo e, em seguida, abaixo da caixa **URL de acesso administrativo** , digite a URL simples que você deseja para acesso administrativo ao Lync Server 2013 painel de controle e clique em **OK**.
    
    <div>
    

    > [!TIP]  
    > Recomendamos usar a URL mais simples possível para a URL Admin. A opção mais simples é <STRONG> https://admin .</STRONG> &lt; domínio &gt; .

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento de URLs simples no Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

