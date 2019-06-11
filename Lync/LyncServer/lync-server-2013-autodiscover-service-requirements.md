---
title: 'Lync Server 2013: Requisitos do serviço de descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea9d9be05561d200696a5ad0256c0d5424cf9b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Requisitos do serviço de descoberta automática para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-25_

O serviço descoberta automática do Microsoft Lync Server 2013 é executado nos servidores do diretor e do pool de front-end e, quando publicados no DNS, pode ser usado por dispositivos móveis que executam o Lync Mobile para localizar serviços de mobilidade. Antes que os dispositivos móveis que executam o Lync Mobile possam tirar proveito da descoberta automática, você precisará modificar listas de nomes alternativos de entidades de certificado em qualquer director e servidor front-end executando o serviço descoberta automática. Além disso, pode ser necessário modificar as listas de nomes alternativos de entidades nos certificados usados para regras de publicação de serviço Web externo em proxies reverso.

Para obter detalhes sobre as entradas de nome alternativo do assunto que são necessárias para os directors, servidores front-end e proxies reverso, consulte [requisitos técnicos de mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) no planejamento para mobilidade.

A decisão sobre o uso de listas de nomes alternativos de entidades em proxies invertidos baseia-se na publicação do serviço de descoberta automática na porta 80 ou na porta 443:

  - **Publicado na porta 80**   nenhuma alteração de certificado será necessária se a consulta inicial para o serviço descoberta automática ocorrer na porta 80. Isso ocorre porque os dispositivos móveis que executam o Lync acessam o proxy reverso na porta 80 externamente e, em seguida, redirecionados para um diretor ou servidor front-end na porta 8080 internamente. Para obter detalhes, consulte a seção "processo de descoberta automática inicial usando a porta 80" mais adiante neste tópico.

  - **Publicado na porta 443**   a lista de nomes alternativos de entidades nos certificados usados pela regra de publicação de serviços Web externos deve conter um *lyncdiscover.\< entrada\> sipdomain* para cada domínio SIP em sua organização.

A emissão de certificados usando uma autoridade de certificação interna geralmente é um processo simples, mas para certificados públicos usados na regra de publicação do serviço Web, adicionar várias entradas de nome alternativo à entidade pode ficar caro. Para contornar esse problema, oferecemos suporte para a conexão de descoberta automática inicial na porta 80, que é redirecionada para a porta 8080 do diretor ou servidor front-end.

Por exemplo, suponha que um cliente móvel que executa o Lync Mobile esteja configurado para entrar no Lync Server 2013 usando o recurso de descoberta automática usando HTTP para a solicitação inicial.

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>Processo de descoberta automática inicial para dispositivos móveis usando a porta 80

1.  O dispositivo móvel que executa o Lync Mobile pesquisa lyncdiscover.contoso.com usando DNS, onde existe um registro A.

2.  DNS externo retorna o endereço IP dos serviços Web externos para o cliente.

3.  O dispositivo móvel que executa o Lync http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com Mobile envia uma solicitação ao proxy reverso

4.  A regra de publicação na Web fará a ponte da porta 80 externamente para a porta 8080 internamente, o que a encaminhará para um diretor ou servidor front-end.
    
    Como a solicitação é HTTP e não HTTPS, nenhuma modificação é necessária para o certificado na regra de publicação de serviço Web externo para dar suporte ao serviço de descoberta automática.

5.  O serviço descoberta automática retorna as URLs do serviço Web externo (em formato HTTPS).

6.  O dispositivo móvel que executa o Lync Mobile poderá reconectar-se ao proxy reverso na porta 443 e será redirecionado sobre o 4443 para o serviço de mobilidade em execução no pool primário do usuário.
    
    Como a consulta HTTPS é para a URL de serviços Web externos versus a URL do serviço de descoberta automática, ela terá êxito porque o certificado já contém entradas de nome alternativo para os serviços Web externos (FQDNs) dos serviços Web externos.
    
    Nesse cenário, não há nenhuma alteração de certificado necessária para dar suporte à mobilidade.
    
    <div>
    

    > [!NOTE]  
    > Se o servidor Web de destino tiver um certificado que não tenha um valor correspondente para lyncdiscover.contoso.com como um valor de lista de nomes alternativos do assunto:<BR>&nbsp;&nbsp;um servidor Web responde com um "servidor Olá"&nbsp;e sem certificado.<BR>b.&nbsp;&nbsp;&nbsp;o dispositivo móvel que executa o Lync Mobile imediatamente finaliza a sessão.<BR>Se o servidor Web de destino tiver um certificado que inclua lyncdiscover.contoso.com como um valor de lista de nomes alternativos do assunto:<BR>&nbsp;&nbsp;um servidor Web responde com uma "saudação de servidor"&nbsp;e um certificado.<BR>b.&nbsp;&nbsp;&nbsp;o dispositivo móvel que executa o Lync Mobile valida o certificado e conclui o handshake.

    
    </div>

Para dar suporte a uma conexão inicial com o serviço de descoberta automática usando a porta 80 em seu servidor proxy reverso, você pode criar uma regra de publicação http semelhante a este exemplo para uma regra de publicação de proxy da Web do Forefront Threat Management Gateway 2010:

1.  Criar uma nova regra de publicação na Web (por exemplo, **descoberta automática do Lync Server (http)**).

2.  Em **nome público**, digite lyncdiscover.contoso.com.

3.  Na guia **ponte** , selecione somente a opção para fazer a ponte de solicitações da porta 80 para a porta 8080.

4.  Na guia **autenticação** , selecione **sem autenticação**, e o **cliente não pode autenticar diretamente**.

5.  Confirme as alterações e mova a regra para a parte superior da lista de regras do Lync (primeiro em ordem de processamento).

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilidade para a implantação de domínio dividido

Um espaço de endereço SIP compartilhado, também conhecido como um *domínio dividido*, ou uma *implantação híbrida* , é uma configuração na qual os usuários são implantados em uma implantação local e em um ambiente online. O resultado desejado é ter um usuário, independentemente de onde o servidor local está localizado (local ou online), fazer logon na implantação e ser redirecionado para o local do servidor de casa. Para fazer isso, o recurso descoberta automática do Microsoft Lync Server 2013 é usado para redirecionar o usuário online para a topologia online. Isso é feito configurando o localizador de recursos uniforme (URL) da descoberta automática usando o Shell de gerenciamento do Lync Server e os cmdlets **Get-CsHostingProvider** e **set-CsHostingProvider**.

Será preciso coletar e gravar os seguintes atributos implantados:

  - No Shell de gerenciamento do Lync Server, digite
    
        Get-CsHostingProvider

  - Nos resultados, localize o provedor online com o atributo **ProxyFQDN**. Por exemplo, sipfed.online.lync.com

  - Gravar o valor do ProxyFQDN

  - Habilite a Federação no painel de controle do Lync Server local, permitindo Federação com o provedor online

  - Habilite a Federação para o provedor online. Por padrão, todos os usuários online estão habilitados para Federação de domínio e podem se comunicar com todos os domínios

  - Se você definirá domínios bloqueados e permitidos, determine os domínios que você permitirá explicitamente ou bloqueará explicitamente

  - Para a Federação online, você deve planejar exceções de firewall, certificados e host DNS (A ou AAAA, se estiver usando IPv6) registros. Além disso, você deve configurar políticas de Federação. Para obter detalhes, consulte [planejando a Federação para o Lync server 2013 e o Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

