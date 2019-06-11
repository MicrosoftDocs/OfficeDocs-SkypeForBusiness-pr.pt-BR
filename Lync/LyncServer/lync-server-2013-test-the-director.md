---
title: 'Lync Server 2013: Testar o Diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f889d548ddc9b177113aa3e395ac181095de8008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>Testar o Diretor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

Neste estágio, você tem um director ou um pool de directors configurado, mas suas entradas de SRV do sistema de nome de domínio (DNS) ainda apontam para os clientes se conectarem usando um servidor pool ou Standard Edition. Antes de alterar o registro DNS para fazer com que os clientes do Lync 2013 façam logon automaticamente usando o diretor, teste um cliente editando-o manualmente para o diretor.

<div>

## <a name="to-test-the-deployment"></a>Para testar a implantação

1.  Faça logon no computador no qual você tem o painel de controle do Lync Server instalado com uma conta de domínio que faça parte do grupo **CSAdministrator** .

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  No painel de navegação, clique em **topologia**e, na coluna **status** , confirme se há um servidor verde com uma seta (ou seja, ![ícone do servidor com]o ícone de servidor de seta verde(images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "com seta verde")) para seu diretor ou pool de diretor.

4.  Conecte dois computadores cliente que tenham o cliente do Lync Server 2013 instalado e faça logon com uma conta de usuário diferente habilitada para o Lync Server 2013 para cada computador.

5.  Em um dos computadores cliente, clique no menu **Opções** , selecione o grupo configurações **pessoais** , clique em **avançado**, clique em **configuração manual**e, em seguida, defina o **nome do servidor interno ou o endereço IP para o endereço IP** totalmente qualificado FQDN (nome de domínio) do novo diretor ou pool do diretor.

6.  Faça logon em ambos os clientes e verifique se o cliente que está fazendo logon usando o diretor é capaz de fazer logon com êxito, veja o status de presença do outro usuário e se ele pode trocar mensagens instantâneas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

