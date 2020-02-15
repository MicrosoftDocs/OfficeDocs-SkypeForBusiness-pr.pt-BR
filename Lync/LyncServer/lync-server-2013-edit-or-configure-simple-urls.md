---
title: 'Lync Server 2013: editar ou configurar URLs simples'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0c36c632e2a2ee33568bd44dd57ec7fc7451343
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>Editar ou configurar URLs simples no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-04_

Este procedimento não exige associação a um grupo de administradores locais ou de domínio privilegiado. Você deve fazer logon em um computador como usuário padrão.

O Lync Server 2013 usa URLs simples para direcionar chamadas internas e externas para serviços no servidor de front-end ou no diretor, se um tiver sido implantado. Para obter mais informações sobre URLs simples, consulte [Planning for Simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) na documentação de planejamento. Você pode selecionar o formato para suas URLs simples a partir de várias opções. Para obter detalhes sobre essas opções, consulte [DNS Requirements for Simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) na documentação de planejamento.

Por padrão, as URLs simples serão configuradas no formato (por exemplo, a URL simples de discagem): https://dialin.\<SIP domínio\>

<div>

## <a name="to-configure-simple-urls"></a>Para configurar URLs simples

1.  No construtor de topologias, clique com o botão direito do mouse no nó **Lync Server** e clique em **Editar propriedades**.

2.  No painel **URLs simples** , selecione URLs de **acesso de telefone:** (discagem) ou **URLs de reunião:** (atender) para editar e clique em **Editar URL**.

3.  Atualize a URL para o valor desejado e clique em **OK** para salvar a URL editada. O exemplo mostrado aqui modificou a URL de discagem para https://pool01.contoso.net/dialin.

4.  Edite a URL de Reunião usando as mesmas etapas, se necessário.

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>Para definir a URL simples Admin opcional

1.  No construtor de topologias, clique com o botão direito do mouse no nó **Lync Server** e clique em **Editar propriedades**.

2.  Na caixa **URL de acesso administrativo** , digite a URL simples que você deseja para acesso administrativo ao painel de controle do Lync Server 2013 e clique em **OK**.
    
    <div>
    

    > [!TIP]  
    > Recomendamos usar a URL mais simples possível para a URL Admin. A opção mais simples é <STRONG> https://admin.</STRONG> &lt;domínio&gt;.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Se você alterar uma URL simples após a implantação inicial, esteja ciente das alterações que afetam seus registros de DNS (Sistema de Nome de Domínio) e certificados para URLs simples. Se a alteração impactar a base de uma URL simples, você deverá alterar os registros DNS e certificados também. Por exemplo, alterar de https://lync.contoso.com/Meet para https://meet.contoso.com altera a URL base de Lync.contoso.com para Meet.contoso.com, portanto, você precisaria alterar os registros DNS e os certificados para fazer referência ao Meet.contoso.com. Se você alterou a URL simples https://lync.contoso.com/Meet de https://lync.contoso.com/Meetingspara, a URL base do Lync.contoso.com permanecerá a mesma, portanto, não serão necessárias alterações de DNS ou de certificado. No entanto, sempre que você alterar um nome de URL simples, deverá executar o cmdlet <STRONG>Enable-CsComputer</STRONG> em cada diretor e servidor front-end para registrar a alteração.

    
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

