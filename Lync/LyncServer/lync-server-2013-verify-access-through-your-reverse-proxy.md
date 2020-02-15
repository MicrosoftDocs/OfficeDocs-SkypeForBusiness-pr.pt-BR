---
title: 'Lync Server 2013: verificar acesso por meio de seu proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dec8a6d5339af93a7e8c0f63aca5f5d3f990583
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>Verificar o acesso por meio de seu proxy reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-29_

Execute o procedimento a seguir para verificar se os usuários podem acessar informações no proxy reverso. Talvez seja necessário concluir a configuração do firewall e do DNS (Sistema de Nomes de Domínio) para que o acesso funcione corretamente.

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>Para verificar se você pode acessar o site via Internet

  - Abra um navegador da Web e, na barra **Endereço**, digite as URLs que são usadas pelos clientes para acessar os arquivos do Catálogo de Endereços e o site de Webconferências da seguinte forma:
    
      - Para o servidor de catálogo de endereços, digite uma URL semelhante à **https://externalwebfarmFQDN/abs** seguinte: onde externalwebfarmFQDN é o FQDN externo dos serviços Web externos que hospeda os serviços de catálogo de endereços. O usuário deve receber um desafio HTTP, pois a segurança do diretório na pasta do Servidor de Catálogo de Endereço está configurada para autenticação do Windows por padrão.
    
      - Para conferência, digite uma URL semelhante à seguinte: **https://externalwebfarmFQDN/meet** onde externalwebfarmFQDN é o FQDN externo do farm da Web que hospeda o conteúdo da reunião. Essa URL deve exibir a página de solução de problemas para conferência. Em alternativa, confirme que sua URL Simples para conferência funcione corretamente. Um exemplo de URL simples para a junção de conferência pode serhttps://meet.contoso.com
    
      - Para expansão de grupo de distribuição, digite uma URL semelhante à seguinte **https://externalwebfarmFQDN/GroupExpansion/service.svc**:. O usuário deve receber um desafio HTTP, pois a segurança do diretório no serviço de expansão do grupo de distribuição está configurada para autenticação do Windows por padrão.
    
      - Para discagem, digite a URL simples semelhante à seguinte **https://externalwebfarmFQDN/dialin** , em que externalwebfarmFQDN é o FQDN externo do farm da Web que hospeda a página de discagem para conferência discada. O usuário deve ser redirecionado para a página de discagem. Em alternativa, confirme que sua discagem de URL simples funcione corretamente. Um exemplo de URL simples para discagem pode serhttps://dialin.contoso.com
    
      - Para confirmar se a URL de descoberta automática está funcionando, https://lyncdiscoverdigite. externaldomainFQDN. O navegador deve solicitar que você abra um arquivo. Selecione o bloco de notas para abri-lo. Uma resposta típica seria semelhante a:
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

