---
title: 'Lync Server 2013: Configurando o repositório de contatos pessoais em computadores cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5672619302e169db5e89281323eec4b5d8312c06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>Configurando o repositório de contatos pessoais em computadores clientes para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-05_

Se você estiver integrando o Microsoft Lync Server 2013 e o Microsoft Exchange Server 2013, recomendamos que você configure o repositório de contatos pessoais em qualquer computador cliente executando o Microsoft Lync 2010. Em particular, você deve configurar o Lync para usar o Exchange como o repositório de contatos pessoais e, ao mesmo tempo, garantir que os usuários não possam substituir essa decisão. Isso pode ser feito criando e configurando um valor de registro em cada computador cliente.

Observe que isso não é necessário em computadores que executam o Lync 2013.

Para configurar esse valor em um único computador, execute os seguinte procedimento:

1.  No computador cliente, clique em **Iniciar** e em **executar**.

2.  Na caixa de diálogo **executar** , digite regedit e pressione Enter.

3.  No editor do registro, expanda **\_hKey local\_Machine**, expanda **software**, expanda **Policies**, expanda **Microsoft**e, em seguida, expanda **Communicator**.

4.  Clique com o botão direito do mouse em **Communicator**, aponte para **novo**e clique em **valor DWORD (32 bits)**.

5.  Depois que o novo valor for criado, digite **PersonalContactStoreOverride** e pressione ENTER para renomear o valor.

6.  Verifique se o valor de PersonalContactStoreOverride está definido para 0 e feche o Editor do Registro.

Se precisar fazer esta mesma alteração em vários computadores, você pode criar um objeto personalizado de Política de Grupo. Para obter detalhes, consulte a documentação da política [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543)de grupo em.

</div>

<span> </span>

</div>

</div>

</div>

