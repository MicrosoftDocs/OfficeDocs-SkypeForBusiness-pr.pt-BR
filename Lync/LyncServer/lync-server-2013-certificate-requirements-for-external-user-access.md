---
title: 'Lync Server 2013: Requisitos de certificado para acesso do usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e7a0802cee8b91e18eaf50e5c2c3942ca54308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Requisitos de certificado para acesso do usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-03-29_

O software de comunicação do Microsoft Lync Server 2013 dá suporte ao uso de um único certificado público para interfaces externas Edge de acesso e Web Conferencing, além do serviço de autenticação A/V. A interface interna Edge geralmente usa um certificado particular emitido por uma autoridade de certificação interna (CA), mas também pode usar um certificado público, desde que ele seja de uma autoridade de certificação pública confiável. O proxy inverso em sua implantação usa um certificado público e criptografa a comunicação do proxy reverso para os clientes e o proxy reverso para servidores internos usando HTTP (ou seja, Transport Layer Security via HTTP).

Veja a seguir os requisitos para o certificado público usado para interfaces externas de Edge de acesso e Web proconferência e o serviço de autenticação A/V:

  - O certificado deve ser emitido por uma autoridade de certificação pública aprovada que seja compatível com o nome alternativo do assunto. Para obter detalhes, consulte o artigo 929395 da base de dados de conhecimento Microsoft, "parceiros de certificado de comunicação unificada [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)para Exchange Server e Communications Server" em.

  - Se o certificado for usado em um pool de bordas, ele deverá ser criado como exportável, com o mesmo certificado usado em cada servidor de borda no pool de borda. O requisito de chave privada de exportável é para os fins do serviço de autenticação A/V, que deve usar a mesma chave privada em todos os servidores de borda do pool.

  - Se você quiser maximizar o tempo de atividade para seus serviços de áudio/vídeo, examine os requisitos de certificado para implementar um certificado de serviço de borda a/V separado (ou seja, um certificado de serviço de borda A/V separado das outras finalidades de certificado de borda externa). Para obter detalhes, consulte [alterações no Lync server 2013 que afetam o planejamento do servidor de borda](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [planejar certificados do servidor de borda no Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) e [preparar certificados AV e OAuth no Lync Server 2013 using-roll Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).

  - O nome do requerente do certificado é o nome de domínio totalmente qualificado do serviço de borda de acesso (FQDN) ou VIP do balanceador de carga de hardware (por exemplo, access.contoso.com). ). O nome do requerente não pode ter um caractere curinga, ele deve ser um nome explícito.
    
    <div>
    

    > [!NOTE]  
    > Para o Lync Server 2013, isso não é mais necessário, mas ainda é recomendado para compatibilidade com o Office Communications Server.

    
    </div>

  - A lista de nomes alternativos de entidades contém os FQDNs dos seguintes:
    
      - A interface externa do serviço de borda do Access ou VIP do balanceador de carga de hardware (por exemplo, sip.contoso.com).
        
        <div>
        

        > [!NOTE]  
        > Embora o nome do requerente do certificado seja igual ao FQDN do conector de acesso, o nome alternativo do assunto também deve conter o FQDN de borda de acesso porque a segurança da camada de transporte (TLS) ignora o nome do assunto e usa as entradas de nome alternativo do assunto para validação.

        
        </div>
    
      - A interface de borda externa Web de Webconferência ou VIP de balanceador de carga de hardware (por exemplo, webcon.contoso.com).
    
      - Se você estiver usando a configuração automática do cliente ou a Federação, inclua também qualquer FQDN do domínio SIP usado dentro da sua empresa (por exemplo, sip.contoso.com, sip.fabrikam.com).
    
      - O serviço de borda A/V não usa as entradas de nome de assunto ou de nomes alternativos de assunto.
    
    <div>
    

    > [!NOTE]  
    > A ordem dos FQDNs na lista nomes alternativos de entidades não importa.

    
    </div>

Se você estiver implantando vários servidores Edge com carga balanceada em um site, o certificado do serviço de autenticação A/V que é instalado em cada servidor de borda deve ser da mesma CA e deve usar a mesma chave privada. Observe que a chave privada do certificado deve ser exportável, independentemente de ser usada em um servidor de borda ou muitos servidores de borda. Ele também deve ser exportável se você solicitar o certificado de qualquer computador que não seja o servidor de borda. Como o serviço de autenticação A/V não usa o nome da entidade ou o nome alternativo do assunto, você pode reutilizar o certificado de borda do Access desde que o nome da entidade e os requisitos de nome alternativo do assunto sejam atendidos para a borda do Access e para a borda de Webconferência e a chave privada do certificado é exportável.

Os requisitos para o certificado privado (ou público) usado para a interface interna de borda são os seguintes:

  - O certificado pode ser emitido por uma autoridade de certificação interna ou uma CA de certificado público aprovada.

  - O nome do requerente do certificado geralmente é o FQDN ou o VIP da interface interna do hardware ou o VIP do balanceador de carga de hardware (por exemplo, lsedge.contoso.com). No entanto, você pode usar um certificado curinga na borda interna.

  - Nenhuma lista de nomes alternativos de entidades é necessária.

O proxy reverso em seus serviços de implantação solicita:

  - Acesso do usuário externo ao conteúdo da reunião para reuniões

  - Acesso de usuário externo para expandir e exibir membros de grupos de distribuição

  - Acesso de usuário externo a arquivos que podem ser baixados do serviço de catálogo de endereços

  - Acesso de usuário externo ao cliente do Lync Web App

  - Acesso de usuário externo à página da Web configurações de conferência discada

  - Acesso de usuário externo ao serviço de informações de localização

  - Acesso do dispositivo externo ao serviço de atualização de dispositivo e obter atualizações

O proxy reverso publica as URLs dos Web Components do servidor interno. As URLs dos Web Components são definidas no director, servidor front-end ou pool de front-end como **Serviços Web externos** no construtor de topologias.

Há suporte para entradas curinga no campo nome alternativo do assunto do certificado atribuído ao proxy reverso. Para obter detalhes sobre como configurar a solicitação de certificado para o proxy reverso, consulte [solicitar e configurar um certificado para seu proxy http reverso no Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).

<div>

## <a name="see-also"></a>Confira também


[Suporte a certificado curinga no Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

