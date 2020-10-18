---
title: 'Lync Server 2013: testar o diretor'
description: 'Lync Server 2013: testar o diretor.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f4cec23be01add5c02cc960cfe68c9256da07d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580207"
---
# <a name="test-the-director-in-lync-server-2013"></a>Testar o diretor no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

Neste estágio, você tem um Diretor ou pool de Diretores configurado, mas as entradas SRV do DNS ainda apontam os clientes para fazer logon usando um pool ou servidor Standard Edition. Antes de alterar o registro DNS para fazer com que os clientes do Lync 2013 façam logon automaticamente usando o diretor, teste um cliente manualmente apontando-o para o diretor.

<div>

## <a name="to-test-the-deployment"></a>Para testar a implantação

1.  Faça logon no computador em que o painel de controle do Lync Server está instalado com uma conta de domínio que faz parte do grupo **CSAdministrator** .

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  No painel de navegação, clique em **topologia**e, na coluna **status** , confirme se há um servidor verde com uma seta (ou seja, ![ícone do servidor com seta verde](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Ícone de servidor com seta verde")) para seu diretor ou pool de diretores.

4.  Conecte dois computadores cliente com o cliente do Lync Server 2013 instalado e faça logon com uma conta de usuário diferente habilitada para o Lync Server 2013 a cada computador.

5.  Em um dos computadores cliente, clique no menu **Opções**, selecione o grupo de configurações **Pessoal**, clique em **Avançado**, em **Configuração Manual** e defina o **Nome do servidor interno ou endereço IP** como o nome totalmente qualificado (FQDN) do novo Diretor ou pool de Diretores.

6.  Faça logon em ambos os clientes e verifique se o cliente que está entrando usando o Diretor consegue fazer logon com êxito, veja o status da presença do outro usuário e se podem trocar mensagens instantâneas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

