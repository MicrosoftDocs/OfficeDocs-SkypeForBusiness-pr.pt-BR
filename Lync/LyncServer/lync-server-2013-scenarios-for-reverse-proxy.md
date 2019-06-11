---
title: 'Lync Server 2013: Cenários de proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1621e8bb0241e82f9f4678d4fe39a4f66f6bcf9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Cenários de proxy reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-21_

Proxies invertidos são necessários no Lync Server 2013 para fornecer acesso a serviços e recursos, como a reunião e URLs de discagem, o catálogo de endereços, o conteúdo da reunião, a expansão da lista de distribuição, os serviços de mobilidade e outros. O cenário de proxy reverso típico no Lync Server 2013 é permitir que clientes externos (por exemplo, o cliente da área de trabalho ou o cliente do Lync Web App) acessem o diretor ou serviços Web externos do servidor front-end.

**Proxy reverso e serviços Web externos**

![13142405-D5C9-45b7-a8b7-a8c89f09c97c] (images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")

Durante a fase de planejamento, você define os requisitos para o proxy reverso em uma implantação do Lync Server 2013. O proxy reverso habilita o acesso aos recursos para os seguintes clientes externos:

  - Cliente de desktop Microsoft Lync 2013

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Aplicativo Lync Windows Store

Ao planejar a implantação do Lync Server 2013, você mapeia os requisitos reais do Lync Server 2013 para os recursos de proxy reverso.

1.  Os clientes externos se conectarão ao proxy reverso na porta TCP 443 e usarão Secure Socket Layer (SSL) ou Transport Layer Security (TLS). Os clientes móveis do Microsoft Lync podem se conectar na porta TCP 80, mas somente quando você executa a conexão inicial com os serviços de descoberta do Lync e o administrador configurou os registros CNAME (ou alias) apropriados do sistema de nomes de domínio (DNS) e aceita que essa a comunicação não será criptografada.

2.  Serviços Web externos do Lync Server 2013 (implantados no servidor front-end e/ou no director) esperam uma conexão de um proxy reverso na porta TCP 4443 e espera que a conexão seja SSL/TLS.
    
    <div>
    

    > [!IMPORTANT]  
    > As portas de escuta padrão sugeridas para os serviços Web externos são TCP 8080 para tráfego HTTP e TCP 4443 para tráfego HTTPS. O construtor de topologias oferece uma oportunidade de substituir os padrões e definir suas próprias portas de escuta para os serviços Web externos. É importante observar que o proxy reverso se comunica com os serviços Web externos, e os clientes externos se comunicam com o proxy reverso. O cliente externo se comunica com o proxy reverso na porta TCP 443, mas você pode redefinir a porta em que o proxy reverso se comunica com os serviços Web externos. As opções no construtor de topologia para substituir as portas de escuta padrão dos serviços Web permitem que você solucione conflitos de portas de escuta que possam surgir na sua infraestrutura.

    
    </div>

3.  Os serviços Web externos do Lync Server 2013 esperam um cabeçalho de host não modificado do cliente para identificar qual serviço e diretório do servidor Web o cliente está tentando usar. As solicitações devem aparecer como se tivessem vindo do proxy reverso

4.  Os serviços Web externos usam diretórios virtuais do servidor Web (vDir) definidos que fornecem os serviços oferecidos aos clientes. Os serviços Web de identificação externa específicos são:
    
      - O vDir "reunião" para reuniões de conferência via Web
    
      - O vDir de "discagem" para acesso por telefone e conferência telefônica
    
      - O vDir de "descoberta automática" do aplicativo Lync da Windows Store, do Lync Mobile e do cliente de desktop Lync 2013. A descoberta automática no Lync Server 2013 é conhecida pelo nome DNS "lyncdiscover"
    
      - Os serviços não definidos são acessados pelo cliente externo por meio de chamadas diretas para os serviços Web externos. Por exemplo, a expansão do grupo de distribuição (DLX) e o serviço de catálogo de endereços (ABS) são acessados por chamadas diretas para os serviços Web externos e vDirs associados. O cliente conhece o caminho real para o vDir e constrói um Uniform Record Locator (URL) com base nessas informações. O cliente acessaria o serviço de catálogo de endereços usando uma URL semelhante a`https://externalweb.contoso.com/abs/handler`
    
      - O Office Web Apps Server quando a conferência é definida e configurada como parte da topologia do Lync Server
        
        <div>
        

        > [!NOTE]  
        > O Office Web Apps Server é um servidor de funções separado e não está configurado como parte dos serviços Web externos. Este servidor é publicado separadamente para acesso de cliente.

        
        </div>

5.  Defina a ponte SSL para cada serviço. A porta externa TCP 443 é mapeada para a porta de serviços Web externos do TCP 4443. Para HTTP não criptografado, a porta TCP 80 é mapeada para a porta TCP 8080 dos serviços Web externos

6.  Planejar os ouvintes de proxy reverso para publicar recursos do servidor Web

7.  Solicite e configure o certificado para o proxy reverso com base nos serviços que serão oferecidos. Se configurado com os nomes alternativos de entidades corretos, este certificado pode ser compartilhado por todos os ouvintes configurados no servidor proxy reverso

Recursos disponíveis para planejar sua implantação de proxy reverso:

  - [Coleta de dados no Lync Server 2013](lync-server-2013-data-collection.md)

  - [Resumo de certificado - Proxy reverso no Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Resumo de porta - Proxy reverso no Lync Server 2013](lync-server-2013-port-summary-reverse-proxy.md)

  - [Resumo de DNS - Proxy reverso no Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

