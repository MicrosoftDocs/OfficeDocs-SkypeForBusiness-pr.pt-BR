---
title: 'Lync Server 2013: Verificar acesso por meio de seu proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e35e3908f66952b0e631484efa590bcd76fc0456
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>Verificar acesso por meio de seu proxy reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-29_

Use o procedimento a seguir para verificar se os usuários podem acessar informações no proxy reverso. Talvez seja necessário concluir a configuração do firewall e a configuração do sistema de nome de domínio (DNS) antes de o Access funcionar corretamente.

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>Para verificar se você pode acessar o site pela Internet

  - Abra um navegador da Web, digite as URLs na barra de **endereços** que os clientes usam para acessar os arquivos do catálogo de endereços e o site para conferência da seguinte maneira:
    
      - Para o servidor do catálogo de endereços, digite uma URL semelhante à **https://externalwebfarmFQDN/abs** seguinte: onde externalwebfarmFQDN é o FQDN externo dos serviços Web externos que hospeda os serviços de catálogo de endereços. O usuário deve receber um desafio HTTP porque a segurança do diretório na pasta do servidor do catálogo de endereços está configurada como autenticação do Windows por padrão.
    
      - Em conferência, digite uma URL semelhante à seguinte: **https://externalwebfarmFQDN/meet** onde externalwebfarmFQDN é o FQDN externo do Web farm que hospeda o conteúdo da reunião. Esta URL deve exibir a página de solução de problemas para conferência. Se preferir, confirme se sua URL simples para a conferência funciona corretamente. Um exemplo de URL simples para a junção em conferência pode serhttps://meet.contoso.com
    
      - Para expansão do grupo de distribuição, digite uma URL semelhante à seguinte **https://externalwebfarmFQDN/GroupExpansion/service.svc**:. O usuário deve receber um desafio HTTP porque a segurança de diretório no serviço de expansão do grupo de distribuição é configurada como autenticação do Windows por padrão.
    
      - Para discagem, digite a URL simples semelhante à seguinte **https://externalwebfarmFQDN/dialin** em que externalwebfarmFQDN é o FQDN externo do Web farm que hospeda a página de discagem para conferência discada. O usuário deve ser direcionado para a página de discagem. Como alternativa, confirme se a sua URL simples de discagem funciona corretamente. Um exemplo de URL simples para discagem pode serhttps://dialin.contoso.com
    
      - Para confirmar se a URL da descoberta automática está funcionando, https://lyncdiscoverdigite. externaldomainFQDN. O navegador deve solicitar a abertura de um arquivo. Selecione bloco de notas para abri-lo. Uma resposta típica seria semelhante a:
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

