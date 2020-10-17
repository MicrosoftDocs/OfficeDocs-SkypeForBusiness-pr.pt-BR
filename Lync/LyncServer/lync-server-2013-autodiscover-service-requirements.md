---
title: 'Lync Server 2013: requisitos do serviço de descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5cf4a26c9f0b36cd239daabbc2538716e2bcd3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515768"
---
# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Requisitos do serviço de descoberta automática para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-25_

O serviço de descoberta automática do Microsoft Lync Server 2013 é executado nos servidores do diretor e do pool de front-ends e, quando publicado no DNS, pode ser usado por dispositivos móveis que executam o Lync Mobile para localizar serviços de mobilidade. Antes que os dispositivos móveis que executam o Lync Mobile possam aproveitar a descoberta automática, você precisa modificar listas de nomes alternativos de entidades de certificado em qualquer diretor e servidor front-end executando o serviço de descoberta automática. Além disso, pode ser necessário modificar as listas de nomes alternativos de entidade nos certificados usados pelas regras de publicação de serviços de Web externa em proxies reversos.

Para obter detalhes sobre as entradas de nome alternativo de entidade que são necessárias para diretores, servidores front-end e proxies reversos, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.

A decisão sobre usar listas de nomes alternativos de entidade em proxies reversos é fundamentada na porta em que o serviço de Descoberta Automática foi publicado, a saber, na porta 80 ou na porta 443:

  - **Publicado na porta 80**     Nenhuma alteração de certificado será necessária se a consulta inicial para o serviço de descoberta automática ocorrer na porta 80. Isso ocorre porque os dispositivos móveis que executam o Lync acessarão o proxy reverso na porta 80 externamente e, em seguida, serão redirecionados para um diretor ou servidor front-end na porta 8080 internamente. Para obter detalhes, consulte a seção “Processo inicial de descoberta automática usando a porta 80” mais adiante, neste tópico.

  - **Publicado na porta 443**     A lista de nomes alternativos da entidade em certificados usados pela regra de publicação dos serviços Web externos deve conter um *lyncdiscover. \<sipdomain\> * entrada para cada domínio SIP em sua organização.

A reemissão de certificados usando uma autoridade de certificado interna geralmente é um processo simples, mas para os certificados públicos usados na regra de publicação do serviço da Web, adicionar várias entradas de nomes alternativos de entidade pode se tornar caro. Para contornar esse problema, oferecemos suporte à conexão de descoberta automática inicial na porta 80, que é então redirecionada para a porta 8080 no diretor ou servidor front-end.

Por exemplo, suponha que um cliente móvel executando o Lync Mobile esteja configurado para entrar no Lync Server 2013 usando o recurso de descoberta automática usando HTTP para a solicitação inicial.

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>Processo de descoberta automática inicial para dispositivos móveis usando a porta 80

1.  O dispositivo móvel que executa o Lync Mobile procura lyncdiscover.contoso.com usando o DNS, onde existe um registro A.

2.  DNS externo retorna o endereço IP dos serviços Web externos para o cliente.

3.  O dispositivo móvel que executa o Lync Mobile envia http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com uma solicitação para o proxy reverso

4.  A regra de publicação na Web preencherá a solicitação da porta 80 externamente para a porta 8080 internamente, que a encaminhará para um diretor ou servidor de front-end.
    
    Uma vez que a solicitação é em HTTP e não HTTPS, não são necessárias modificações para o certificado na regra de publicação de serviço da Web externa para suportar o serviço de descoberta automática.

5.  O serviço de Descoberta Automática retorna os URLs do serviço de Web externa (em formato HTTPS).

6.  O dispositivo móvel que executa o Lync Mobile pode se reconectar ao proxy reverso na porta 443 e é redirecionado sobre 4443 para o serviço de mobilidade em execução no pool local do usuário.
    
    Uma vez que a consulta do HTTPS é sobre o URL dos serviços de Web externa versus o URL do serviço de descoberta automática, ela é bem-sucedida, pois o certificado já deve conter entradas de nomes alternativos de entidade para os FQDNs (nomes de domínio totalmente qualificados) de serviços Web externos.
    
    Neste cenário, não há alterações necessárias para dar suporte à mobilidade.
    
    <div>
    

    > [!NOTE]  
    > Se o servidor Web de destino possuir um certificado que não tenha um valor de correspondência para lyncdiscover.contoso.com como um valor de lista de nome alternativo de entidade:<BR>um. &nbsp; &nbsp; &nbsp; O servidor Web responde com uma "saudação de servidor" e nenhum certificado.<BR>b. &nbsp; &nbsp; &nbsp; O dispositivo móvel que executa o Lync Mobile interrompe imediatamente a sessão.<BR>Se o servidor da Web de destino tiver um certificado que inclui lyncdiscover.contoso.com como valor de lista de nome alternativo de entidade:<BR>um. &nbsp; &nbsp; &nbsp; O servidor Web responde com uma "saudação de servidor" e um certificado.<BR>b. &nbsp; &nbsp; &nbsp; O dispositivo móvel que executa o Lync Mobile valida o certificado e conclui o handshake.

    
    </div>

Para dar suporte a uma conexão inicial ao serviço de descoberta automática usando a porta 80 no seu servidor de proxy reverso, você pode criar uma regra de publicação de http semelhante a este exemplo para uma regra de publicação de proxy reverso do Forefront Threat Management Gateway 2010:

1.  Crie uma nova regra de publicação da Web (por exemplo, **Descoberta Automática do Lync Server (HTTP)**).

2.  Em **Nome Público**, insira lyncdiscover.contoso.com.

3.  Na guia **Ponte**, selecione apenas a opção das solicitações de ponte da Porta 80 à Porta 8080.

4.  Na guia **Autenticação**, selecione **Sem autenticação** e **Cliente não pode autenticar diretamente**.

5.  Confirme as alterações e mova a regra para a parte superior da lista de regras do Lync (primeiro na ordem de processamento).

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilidade para a Implantação de domínio dividido

Um espaço de endereço SIP compartilhado, também conhecido como *domínio dividido* ou *implantação híbrida* é uma configuração na qual os usuários são implantados em uma implantação local e um ambiente online. O resultado desejado é ter um usuário, independentemente de onde seu servidor doméstico esteja localizado (local ou online), para fazer logon na implantação e ser redirecionado ao local de seu servidor doméstico. Para fazer isso, o recurso de descoberta automática do Microsoft Lync Server 2013 é usado para redirecionar o usuário online para a topologia online. Isso é feito configurando o localizador de recursos uniforme (URL) de descoberta automática usando o Shell de gerenciamento do Lync Server e os cmdlets **Get-CsHostingProvider** e **set-CsHostingProvider**.

Será necessário coletar e registrar os seguintes atributos implantados:

  - No Shell de gerenciamento do Lync Server, digite
    
        Get-CsHostingProvider

  - Nos resultados, encontre o provedor online com o atributo **ProxyFQDN**. Por exemplo, sipfed.online.lync.com

  - Registre o valor do ProxyFQDN

  - Habilitar Federação no painel de controle do Lync Server local, permitindo Federação com o provedor online

  - Habilite a federação para o provedor online. Por padrão, todos os usuários online são habilitados para federação de domínio e podem se comunicar com todos os domínios

  - Se você for definir domínios bloqueados e permitidos, determine os domínios que permitirá ou bloqueará explicitamente

  - Para federação online, é necessário planejar exceções de firewall, certificados e registros de host DNS (A ou AAAA, se estiver usando IPv6). Além disso, é necessário configurar as políticas de federação. Para obter detalhes, consulte [Planning for Lync server 2013 and Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

