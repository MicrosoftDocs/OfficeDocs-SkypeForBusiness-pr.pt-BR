---
title: 'Lync Server 2013: requisitos de configuração para proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13026da5515615610c960fe4648d5c58f64f99fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Requisitos de configuração para o proxy reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-05_

O Lync Server 2013 impõe alguns requisitos em comunicações do cliente externo que são passados para os serviços Web externos hospedados no diretor, pool de diretores, servidor front-end ou pool de front-ends. O proxy reverso também é responsável por publicar o servidor do Office Web Apps, se você estiver oferecendo conferência para seus usuários.

<div>


> [!NOTE]  
> O Lync Server 2013 não especifica um determinado proxy reverso que você deve usar. O Lync Server 2013 só define os requisitos operacionais que o proxy reverso deve ser capaz de fazer. Normalmente, o proxy reverso que você já implantou em sua infraestrutura pode ser capaz de atender aos requisitos.



</div>

<div>

## <a name="reverse-proxy-requirements"></a>Requisitos de proxy reverso

As operações funcionais que o Lync Server 2013 esperam que um proxy reverso seja executado são:

  - Use SSL (Secure Socket Layer) e TLS (Transport Layer Security) implementados usando certificados adquiridos de uma autoridade de certificação pública para se conectar aos serviços Web externos publicados do diretor, pool de diretores, servidor front-end ou pool de front-ends. O diretor e o servidor front-end podem estar em um pool com balanceamento de carga usando balanceadores de carga de hardware.

  - É possível publicar sites internos usando certificados para criptografia ou publicá-los por meio de um meio não criptografado, se necessário.

  - Capaz de publicar um site da Web hospedado internamente externamente usando um FQDN (nome de domínio totalmente qualificado).

  - Capaz de publicar todo o conteúdo do site hospedado. Por padrão, você pode usar a ** / ** diretiva, que é reconhecida pela maioria dos servidores Web para significar "publicar todo o conteúdo no servidor Web". Você também pode modificar a diretiva — por exemplo, **/Uwca/\***, que significa "publicar todo o conteúdo sob o diretório virtual Ucwa."

  - Deve ser configurável para exigir conexões SSL (Secure Sockets Layer) e/ou TLS (Transport Layer Security) com clientes que solicitam conteúdo de um site publicado.

  - Deve aceitar certificados com entradas de nome alternativo de entidade (SAN).

  - Deve ser capaz de permitir a associação de um certificado a um ouvinte ou a uma interface por meio da qual o FQDN de serviços Web externos resolverá. As configurações de escuta são preferidas para interfaces. Muitos ouvintes podem ser configurados em uma única interface.

  - Deve permitir a configuração do controle de cabeçalho de host. Geralmente, o cabeçalho de host original enviado pelo cliente solicitante deve ser passado de forma transparente, em vez de ser modificado pelo proxy reverso.

  - Ponte de tráfego SSL e TLS de uma porta definida externamente (por exemplo, TCP 443) para outra porta definida (por exemplo, TCP 4443). O proxy reverso pode descriptografar o pacote no recebimento e, em seguida, criptografar novamente o pacote no envio.

  - A ponte de tráfego TCP não criptografado de uma porta (por exemplo, TCP 80) para outra (por exemplo, TCP 8080).

  - Permitir a configuração ou aceitar a autenticação NTLM, sem autenticação e autenticação de passagem.

</div>

</div>

<span> </span>

</div>

</div>

</div>

