---
title: 'Lync Server 2013: cenários para proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 767df1e427cd29e9437b4bd04d2859b382b48267
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510828"
---
# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Cenários de proxy reverso no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-21_

Os proxies reversos são necessários no Lync Server 2013 para fornecer acesso a serviços e recursos como as URLs de reunião e discagem, o catálogo de endereços, o conteúdo da reunião, a expansão da lista de distribuição, os serviços de mobilidade e outros. O cenário de proxy reverso típico no Lync Server 2013 é permitir que clientes externos (por exemplo, o cliente da área de trabalho ou o cliente do Lync Web App) acessem o diretor ou serviços Web externos do servidor front-end.

**Proxy reverso e serviços Web externos**

![13142405-D5C9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")

Durante a fase de planejamento, você define os requisitos para o proxy reverso em uma implantação do Lync Server 2013. O proxy reverso permite o acesso a recursos para os seguintes clientes externos:

  - Cliente de desktop do Microsoft Lync 2013

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Aplicativo Lync da Windows Store

Ao planejar sua implantação do Lync Server 2013, você mapeia os requisitos reais do Lync Server 2013 para os recursos de proxy reverso.

1.  Os clientes externos se conectarão ao proxy reverso na porta TCP 443 e usarão Secure Socket Layer (SSL) ou Transport Layer Security (TLS). Os clientes móveis do Microsoft Lync podem se conectar na porta TCP 80, mas somente quando se executa a conexão inicial com os serviços de descoberta do Lync e o administrador configurou os registros CNAME (ou alias) adequados do sistema de nomes de domínio (DNS) e aceita que essa comunicação não será criptografada.

2.  Lync Server 2013 serviços Web externos (implantados no servidor front-end e/ou no diretor) esperam uma conexão de um proxy reverso na porta TCP 4443 e espera que a conexão seja SSL/TLS.
    
    <div>
    

    > [!IMPORTANT]  
    > As portas de escuta padrão sugeridas para os serviços Web externos são TCP 8080 para tráfego HTTP e TCP 4443 para tráfego HTTPS. O construtor de topologias oferece uma oportunidade de substituir os padrões e definir suas próprias portas de escuta para os serviços Web externos. É importante observar que o proxy reverso se comunica com os serviços Web externos e os clientes externos se comunicam com o proxy reverso. O cliente externo se comunica com o proxy reverso na porta TCP 443, mas você pode redefinir de que porta o proxy reverso se comunica com os serviços Web externos. As opções no construtor de topologia para substituir as portas de escuta padrão para os serviços Web permitem resolver conflitos de porta de escuta que podem surgir em sua infraestrutura.

    
    </div>

3.  Lync Server 2013 serviços Web externos esperam um cabeçalho de host não modificado do cliente para identificar qual serviço e diretório de servidor Web o cliente está tentando usar. As solicitações devem aparecer como se tivessem vindo do proxy reverso

4.  Os serviços Web externos usam diretórios virtuais de servidor Web (vDir) definidos que fornecem os serviços oferecidos aos clientes. Os serviços Web específicos identificáveis externamente são:
    
      - O vDir de "reunião" para reuniões de conferência via Web
    
      - O vDir de "discagem" para acesso por telefone e conferência telefônica
    
      - O vDir de "descoberta automática" do aplicativo Lync da Windows Store, Lync Mobile e cliente de desktop Lync 2013. A descoberta automática no Lync Server 2013 é conhecida pelo nome DNS "lyncdiscover"
    
      - Os serviços não definidos são acessados pelo cliente externo por chamadas diretas para os serviços Web externos. Por exemplo, a expansão de grupo de distribuição (DLX) e o serviço de catálogo de endereços (ABS) são acessados por chamadas diretas para os serviços Web externos e vDirs associados. O cliente sabe o caminho real para o vDir e constrói um localizador de registro uniforme (URL) com base nessas informações. O cliente acessaria o serviço de catálogo de endereços usando uma URL semelhante à `https://externalweb.contoso.com/abs/handler`
    
      - O servidor do Office Web Apps quando a conferência é definida e configurada como parte da topologia do Lync Server
        
        <div>
        

        > [!NOTE]  
        > O servidor do Office Web Apps é um servidor de função separado e não está configurado como parte dos serviços Web externos. Este servidor é publicado separadamente para acesso para cliente.

        
        </div>

5.  Defina ponte SSL para cada serviço. A porta externa TCP 443 é mapeada para a porta de serviços Web externos de TCP 4443. Para HTTP não criptografado, a porta TCP 80 é mapeada para a porta TCP 8080 de serviços Web externos

6.  Planejar os ouvintes de proxy reverso para publicar recursos de servidor Web

7.  Solicite e configure o certificado para o proxy reverso com base nos serviços que serão oferecidos. Se estiver configurado com os nomes alternativos de entidade corretos, esse certificado poderá ser compartilhado por todos os ouvintes configurados no servidor de proxy reverso

Recursos disponíveis para planejar a implantação do seu proxy reverso:

  - [Coleta de dados no Lync Server 2013](lync-server-2013-data-collection.md)

  - [Resumo de certificado-proxy reverso no Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Resumo de porta-proxy reverso no Lync Server 2013](lync-server-2013-port-summary-reverse-proxy.md)

  - [Resumo de DNS-proxy reverso no Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

