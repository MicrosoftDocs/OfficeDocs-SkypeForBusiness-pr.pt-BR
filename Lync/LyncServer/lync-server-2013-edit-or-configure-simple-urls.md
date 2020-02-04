---
title: 'Lync Server 2013: Editar ou configurar URLs simples'
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
ms.openlocfilehash: 0fe6ae7197e2f47c590384547c34dd4b1db50950
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>Editar ou configurar URLs simples no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-04_

Esse procedimento não requer associação em um administrador local ou em um grupo de domínio privilegiado. Você deve fazer logon em um computador como usuário padrão.

O Lync Server 2013 usa URLs simples para direcionar chamadas internas e externas para serviços no servidor front-end ou no director, se um foi implantado. Para obter mais informações sobre URLs simples, consulte [planejando URLs simples no Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) na documentação de planejamento. Você pode selecionar o formato de suas URLs simples a partir de várias opções. Para obter detalhes sobre essas opções, consulte [requisitos de DNS para URLs simples no Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) na documentação de planejamento.

Por padrão, as URLs simples serão configuradas na forma de (por exemplo, a URL simples de discagem) https://dialin.\<SIP : domínio\>

<div>

## <a name="to-configure-simple-urls"></a>Para configurar URLs simples

1.  No construtor de topologias, clique com o botão direito do mouse no nó do **Lync Server** e, em seguida, clique em **Editar propriedades**.

2.  No painel **URLs Simples**, selecione **URLs de acesso telefônico:** (Discagem) ou **URLs de Reunião:** (Reunião) para editar. Em seguida, clique em **Editar URL**.

3.  Atualize a URL para o valor desejado e clique em **OK** para salvar a URL editada. O exemplo mostrado aqui modificou a URL de discagem para https://pool01.contoso.net/dialin.

4.  Siga as mesmas etapas para editar a URL de Reunião, se necessário.

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>Para definir a URL simples Admin opcional

1.  No construtor de topologias, clique com o botão direito do mouse no nó do **Lync Server** e, em seguida, clique em **Editar propriedades**.

2.  Na caixa **URL de acesso administrativo** , insira a URL simples que você deseja para ter acesso administrativo ao painel de controle do Lync Server 2013 e clique em **OK**.
    
    <div>
    

    > [!TIP]  
    > Nós recomendamos que você use a URL do administrador mais simples possível. A opção mais simples é <STRONG> https://admin.</STRONG> &lt;domínio&gt;.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Se alterar uma URL simples após a implantação inicial, você deve saber quais alterações afetam os registros de DNS e os certificados das URLs simples. Se a alteração impactar a base de uma URL simples, você deve também alterar os registros DNS e certificados. Por exemplo, mudar de https://lync.contoso.com/Meet para https://meet.contoso.com altera a URL base de Lync.contoso.com para Meet.contoso.com, portanto, você precisaria alterar os registros DNS e os certificados para se referirem ao Meet.contoso.com. Se você alterou a URL simples https://lync.contoso.com/Meet de https://lync.contoso.com/Meetingspara, a URL base de Lync.contoso.com permanece a mesma, portanto, não é necessária nenhuma alteração de DNS ou certificado. No entanto, sempre que você alterar um nome de URL simples, você deve executar o cmdlet <STRONG>Enable-CsComputer</STRONG> em cada director e servidor front-end para registrar a alteração.

    
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

