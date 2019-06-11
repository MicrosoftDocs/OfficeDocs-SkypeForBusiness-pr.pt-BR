---
title: 'Lync Server 2013: requisitos de configuração para proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0367ea79a0f3de6ad716f18aab980e9d9442e148
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Requisitos de configuração para o proxy inverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-05_

O Lync Server 2013 imponha alguns requisitos sobre comunicações do cliente externo que, em seguida, passaram para os serviços Web externos hospedados no director, pool do diretor, servidor front-end ou pool de front-ends. O proxy inverso também é responsável por publicar o servidor do Office Web Apps, se você estiver oferecendo conferências para seus usuários.

<div>


> [!NOTE]  
> O Lync Server 2013 não especifica um determinado proxy reverso que você deve usar. O Lync Server 2013 define somente requisitos operacionais que o proxy reverso deve ser capaz de fazer. Geralmente, o proxy inverso que você já implantou na sua infraestrutura pode atender aos requisitos.



</div>

<div>

## <a name="reverse-proxy-requirements"></a>Requisitos de proxy reverso

As operações funcionais que o Lync Server 2013 esperam que um proxy reverso execute:

  - Use Secure Socket Layer (SSL) e Transport Layer Security (TLS) implementado usando certificados adquiridos de uma autoridade de certificação pública para se conectar aos serviços Web externos publicados do diretor, do pool de director, do servidor front-end ou do pool de front-ends. O diretor e o servidor front-end podem estar em um pool de balanceamento de carga usando balanceadores de carga de hardware.

  - Pode publicar sites internos usando certificados para criptografia ou publicá-los por meio de um meio não criptografado, se necessário.

  - Capaz de publicar um site da Web hospedado internamente externamente usando um FQDN (nome de domínio totalmente qualificado).

  - Pode publicar todo o conteúdo do site hospedado. Por padrão, você pode usar a ** / ** diretiva, que é reconhecida pela maioria dos servidores Web, para significar "publicar todo o conteúdo no servidor Web". Você também pode modificar a diretiva — por exemplo, **/Uwca/\***, que significa "publicar todo o conteúdo sob o diretório virtual Ucwa".

  - Deve ser configurável para exigir conexões SSL (Secure Sockets Layer) e/ou Transport Layer Security (TLS) com clientes que solicitam conteúdo de um site publicado.

  - Deve aceitar certificados com entradas de nome alternativo de assunto (SAN).

  - Deve ser capaz de permitir a associação de um certificado a um ouvinte ou interface por meio do qual o FQDN de serviços Web externos irá resolver. Configurações de ouvinte são preferíveis para interfaces. Muitos ouvintes podem ser configurados em uma única interface.

  - Deve permitir a configuração do controle de cabeçalho de host. Geralmente, o cabeçalho original do host enviado pelo cliente solicitante deve ser passado de forma transparente, em vez de ser modificado pelo proxy reverso.

  - A ponte do tráfego SSL e TLS de uma porta definida externamente (por exemplo, TCP 443) para outra porta definida (por exemplo, TCP 4443). O proxy reverso pode descriptografar o pacote no recebimento e, em seguida, criptografar novamente o pacote no envio.

  - Conexão de tráfego TCP não criptografado de uma porta (por exemplo, TCP 80) para outro (por exemplo, TCP 8080).

  - Permitir a configuração ou aceitar autenticação NTLM, sem autenticação e autenticação de passagem.

</div>

</div>

<span> </span>

</div>

</div>

</div>

