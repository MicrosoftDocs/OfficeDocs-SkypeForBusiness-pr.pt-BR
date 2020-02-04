---
title: Alterar URLs simples após a migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: a24eda274734e0c5a27fab30640a363de6653514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>Alterar URLs simples após a migração

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-22_

O Lync Server oferece suporte a três URLs simples:

  - A **reunião** é usada como a URL base para todas as conferências no site ou na organização. Com a URL simples de reunião, os links para ingressar em reuniões são fáceis de compreender e fáceis de se comunicar e distribuir.

  - A **discagem** permite o acesso à página da Web configurações de conferência discada. A URL simples Dial-in é incluída em todos os convites de reunião para que os usuários que desejam discar para a reunião possam acessar o número de telefone e as informações de PIN necessárias.

  - O **administrador** habilita o acesso rápido ao painel de controle do Lync Server. A URL simples de Admin é parte interna da sua organização.

Depois de migrar para o Lync Server 2013, você deve estar ciente de como a alteração afeta seus registros DNS e certificados para URLs simples. Se o diretor herdado do Lync Server 2010 permanecer em uso na topologia, nenhuma alteração nas suas URLs simples será necessária. Se o diretor do Lync Server 2010 for removido da topologia após a migração, os registros DNS de URL simples deverão ser atualizados para apontar para um dos pools do Lync Server 2013. No entanto, sempre que você alterar um nome de URL simples, você deve executar Enable-CsComputer em cada director e servidor front-end para registrar a alteração.

<div>

## <a name="changing-simple-urls-after-migration"></a>Alterar URLs simples após a migração

**Para atualizar a URL de reunião simples**

1.  No construtor de topologias, clique com o botão direito do mouse no nó superior do **Lync Server**e clique em **Editar propriedades**.

2.  Selecione **URLs simples** no painel esquerdo e, abaixo de **URLs de reunião:** selecione a URL do encontro e clique em **Editar URL**.

3.  Atualize a URL para o valor desejado e clique em **OK** para salvar a URL editada.

**Para atualizar a URL simples de administrador**

1.  No construtor de topologias, clique com o botão direito do mouse no nó superior do **Lync Server**e clique em **Editar propriedades**.

2.  Selecione **URLs simples** no painel esquerdo e, em seguida, abaixo da caixa **URL de acesso administrativo** , insira a URL simples que você deseja para acessar o painel de controle do Lync Server 2013 e clique em **OK**.
    
    <div>
    

    > [!TIP]  
    > Nós recomendamos que você use a URL do administrador mais simples possível. A opção mais simples é <STRONG> https://admin.</STRONG> &lt;domínio&gt;.

    
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

