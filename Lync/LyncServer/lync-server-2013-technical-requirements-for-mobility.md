---
title: 'Lync Server 2013: requisitos técnicos para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb4c1eacf48940822ddb26ac41f238ccdb4452dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Requisitos técnicos para mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Os usuários de dispositivos móveis encontram vários cenários de aplicativos de dispositivos móveis que requerem planejamento especial. Por exemplo, alguém pode começar a usar um aplicativo móvel enquanto estiver distante do trabalho conectando-se através da rede 3G e, em seguida, alterne para a rede Wi-Fi corporativa ao chegar no trabalho e, em seguida, volte para 3G ao sair do edifício. Você precisa planejar seu ambiente para suportar tais transições da rede e garantir uma experiência de usuário consistente. Esta seção descreve os requisitos de infraestrutura que você deve ter para dar suporte a aplicativos móveis e descoberta automática de recursos de mobilidade.

<div>


> [!NOTE]  
> Embora os aplicativos móveis também possam se conectar a outros serviços do Lync Server 2013, o requisito para enviar todas as solicitações da Web do aplicativo móvel para o mesmo nome de domínio totalmente qualificado (FQDN) da Web externa aplica-se apenas ao serviço de mobilidade do Lync Server 2013. Outros serviços de mobilidade não exigem essa configuração.



</div>

O requisito para afinidade de cookie nos balanceadores de carga de hardware é reduzido drasticamente e você substitui a afinidade TCP (Transmission Control Protocol) se estiver usando o Lync Mobile fornecido com o Lync Server 2013. A afinidade de cookies ainda pode ser usada, mas os serviços Web não precisam mais dela.

<div>


> [!IMPORTANT]  
> Todo o tráfego do serviço de mobilidade passa pelo proxy reverso, independentemente de onde o ponto de origem seja — interno ou externo. No caso de um único proxy reverso ou de um farm de proxies reversos, ou um dispositivo que está fornecendo a função de proxy reverso, pode surgir um problema quando o tráfego interno está se estornando por meio de uma interface e tentando entrar imediatamente na mesma interface. Isso geralmente leva a uma violação de regra de segurança conhecida como falsificação de pacotes TCP ou apenas spoofing. A <EM>fixação de cabelo</EM> (o egresso e os ingress imediatos de um pacote ou uma série de pacotes) devem ser permitidas para que a mobilidade funcione. Uma maneira de resolver esse problema é usar um proxy reverso separado do firewall (a regra de prevenção de falsificação deve sempre ser imposta no firewall, para fins de segurança). O hairpin pode ocorrer na interface externa do proxy reverso, em vez da interface externa do firewall. Você detecta a falsificação no firewall e libera a regra no proxy reverso, permitindo assim que o hairpin que a mobilidade exija.<BR>Use o host DNS (sistema de nomes de domínio) ou registros CNAME para definir o proxy reverso para o comportamento hairpin (não o firewall), se possível.



</div>

O Lync Server 2013 oferece suporte a serviços de mobilidade para clientes móveis do Lync 2010 Mobile e Lync 2013. Ambos os clientes usam o serviço de descoberta automática do Lync Server 2013 para encontrar o ponto de entrada de mobilidade, mas diferem em qual serviço de mobilidade eles usam. Lync 2010 Mobile usa o serviço de mobilidade conhecido como *MCX*, introduzido com a atualização cumulativa para o Lync Server 2010: novembro de 2011. Os clientes móveis do Lync 2013 usam a API da Web de comunicações unificadas ou o *UCWA*, como provedor de serviços de mobilidade.

<div>

## <a name="internal-and-external-dns-configuration"></a>Configuração de DNS interna e externa

Os serviços de mobilidade MCX (introduzidos com a atualização cumulativa do Lync Server 2010: novembro de 2011) e UCWA (introduzidos nas atualizações cumulativas do Lync Server 2013: fevereiro de 2013) usam o DNS da mesma maneira.

Quando você usa a descoberta automática, os dispositivos móveis usam o DNS para localizar recursos. Durante a pesquisa de DNS, é feita uma primeira tentativa de conexão com o FQDN associado ao registro DNS interno (lyncdiscoverinternal.\< nome\>de domínio interno). Se não for possível fazer uma conexão usando o registro DNS interno, será feita uma tentativa de conexão usando o registro DNS externo (lyncdiscover.\< sipdomain\>). Um dispositivo móvel que é interno à rede se conecta à URL interna do Serviço Descoberta Automática e um dispositivo móvel que é externo à rede se conecta à URL externa do Serviço de Descoberta Automática. As solicitações de descoberta automática externa passam pelo proxy reverso. O serviço de descoberta automática do Lync Server 2013 retorna todas as URLs de serviços Web para o pool inicial do usuário, incluindo as URLs do serviço de mobilidade (MCX e UCWA). No entanto, a URL interna do serviço de dispositivos móveis e a URL externa do serviço de de dispositivos móveis estão associados com o FQDN de Serviços Web externos. Portanto, independentemente de um dispositivo móvel ser interno ou externo à rede, o dispositivo sempre se conecta ao serviço de mobilidade do Lync Server 2013 externamente através do proxy reverso.

<div>


> [!NOTE]  
> É importante entender que sua implantação pode consistir em vários namespaces distintos para uso interno e externo. O nome de domínio SIP pode ser diferente do nome de domínio de implantação interna. Por exemplo, seu domínio SIP pode ser <STRONG>contoso.com</STRONG>, enquanto sua implantação interna pode ser <STRONG>contoso.net</STRONG>. Os usuários que fizerem logon no Lync Server usarão o nome de domínio SIP, como <STRONG>John@contoso.com</STRONG>. Ao lidar com os serviços Web externos (definidos no construtor de topologias como <STRONG>Serviços Web externos</STRONG>), o nome de domínio e o nome de domínio SIP serão consistentes, conforme definido no DNS. Ao lidar com os serviços Web internos (definidos no construtor de topologias como <STRONG>Serviços Web internos</STRONG>), o nome padrão dos serviços Web internos será o FQDN do servidor front-end, do front-end, do diretor ou do pool de diretores. Você tem a opção de substituir o nome dos serviços Web internos. Você deve usar o nome de domínio interno (e não o nome de domínio SIP) para serviços Web internos e definir o host DNS A (ou, para IPv6, AAAA) para refletir o nome substituído. Por exemplo, o FQDN de serviços Web internos padrão pode ser <STRONG>pool01.contoso.net</STRONG>. Um FQDN de serviços Web internos substituído pode ser <STRONG>webpool.contoso.net</STRONG>. Definir os serviços Web dessa forma ajuda a garantir que a localidade interna e externa dos serviços, e não a localidade do usuário que os está usando, seja observada.<BR>No entanto, como os serviços Web são definidos no construtor de topologias e o nome de serviços Web internos pode ser substituído, contanto que o nome dos serviços Web resultantes, o certificado que o valida e os registros DNS que os definem, sejam consistentes, você pode definir o serviços Web internos com qualquer nome de domínio, incluindo o nome de domínio SIP, que você deseja. Em última análise, a resolução do nome para o endereço IP é determinada pelos registros de host DNS e por um namespace consistente.<BR>Para os fins deste tópico e os exemplos, o nome de domínio interno é usado para ilustrar a topologia e as definições de DNS.



</div>

O diagrama a seguir ilustra o fluxo de solicitações da Web de aplicativo móvel para o serviço de mobilidade e para o serviço de descoberta automática ao usar uma configuração de DNS interna e externa.

**Fluxo de serviço de mobilidade usando a descoberta automática**

![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> O diagrama ilustra os serviços Web genéricos. Um diretório virtual chamado Mobility representa os serviços de mobilidade MCX e/ou UCWA. Se você não aplicou as atualizações cumulativas do Lync Server 2013:2013 de fevereiro, você pode ou não ter o diretório virtual Ucwa definido em seus serviços Web internos e externos. Você terá uma descoberta automática de diretório virtual e poderá ter um diretório virtual MCX.<BR>A descoberta automática e a descoberta de serviços funcionam da mesma forma, independentemente da tecnologia de serviços de mobilidade que você implantou.



</div>

Para ofrecer suporte aos usuários de dispositivos móveis de dentro e fora da rede corporativa, os FQDNs de web interno e externo devem atender a alguns pré-requisitos. Além disso, talvez você precise atender a outros requisitos, dependendo dos recursos escolhidos para implementar:

  - Novos registros DNS, CNAME ou A (host, se IPv6, AAAA), para descoberta automática.

  - Nova regra de firewall, se você quiser dar suporte a notificações por push através da sua rede Wi-Fi.

  - Nomes alternativos de entidade em certificados de servidor interno e certificados de proxy reverso, para descoberta automática.

  - Configuração do balanceador de carga de hardware do servidor front-end altera a afinidade de origem.

Sua topologia deve atender aos seguintes requisitos para dar suporte ao serviço de mobilidade e ao serviço de descoberta automática:

  - O FQDN interno da Web do pool de front-ends deve ser diferente do FQDN externo da Web do pool de front-ends.

  - O FQDN interno da web somente deve resolver à rede corporativa e ser acessível a partir dela .

  - O FQDN da Web externo deve apenas resolver e ser acessível a partir da Internet.

  - Para um usuário que está dentro da rede corporativa, a URL do Serviço de Mobility deverá ser direcionada ao FQDN externo da web. Este requisito é para o Serviço de Mobility e se aplica somente a esta URL.

  - Para um usuário que está fora da rede corporativa, a solicitação deve ir para o FQDN externo da Web do pool ou diretor de front-ends.

Se você oferecer suporte à descoberta automática, será necessário criar os seguintes registros DNS para cada domínio SIP:

  - Um registro DNS interno para dar suporte a usuários móveis que se conectam de dentro da rede da sua organização.

  - Um registro DNS externo ou público para suportar usuários móveis que se conectam a partir da Internet.

A URL de descoberta automática interna não deve ser endereçável de fora da rede. A URL de descoberta automática externa não deve ser endereçável de dentro da rede. No entanto, se você não puder atender a esse requisito para a URL externa, o cliente móvel provavelmente não será afetado, porque a URL interna é sempre tentada primeiro.

Os registros DNS podem ser registros CNAME ou registros A (host, se IPv6, AAAA).

<div>


> [!NOTE]  
> Os clientes de dispositivo móvel não suportam vários certificados de SSL (Secure Sockets Layer) de domínios diferentes. Portanto, não há redirecionamento CNAME para diferentes domínios por HTTPS. Por exemplo, um registro DNS CNAME para lyncdiscover.contoso.com que redireciona a um endereço de director.contoso.net não é suportado por HTTPS. Na topologia, um cliente de dispositivo móvel precisa usar HTTP para a primeira solicitação, para que o redirecionamento de CNAME seja resolvido por HTTP. As solicitações subseqüentes usam HTTPS. Para oferecer suporte a esse cenário, você precisará configurar o proxy inverso com uma regra de publicação na web para a porta 80 (HTTP). Para obter detalhes, consulte "criar uma regra de publicação na Web para a porta 80" em <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configurando o proxy reverso para mobilidade no Lync Server 2013</A>.<BR>O redirecionamento de CNAME ao mesmo domínio é suportado por HTTPS. Nesse caso, o certificado do domínio de destino abrange o domínio de origem.



</div>

Para obter detalhes sobre os registros DNS necessários para o seu cenário, confira [Resumo de DNS-descoberta automática no Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).

</div>

<div>

## <a name="port-and-firewall-requirements"></a>Requisitos de Firewall e de Porta

Se você oferecer suporte a notificações por push e quiser que os dispositivos móveis da Apple recebam notificações por push em sua rede Wi-Fi, você também precisará abrir a porta 5223 na sua rede Wi-Fi corporativa. A porta 5223 é uma porta TCP de saída usada pelo Apple Push Notification Service (APNS). O dispositivo móvel inicia a conexão. Para obter detalhes, [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) consulte.

<div>


> [!WARNING]  
> Um dispositivo Apple que usa o cliente móvel do Lync 2013 não requer notificações por push.



</div>

Observe que, se um usuário for hospedado em um aparelho de filial persistente (SBA), as seguintes portas são necessárias:

  - UcwaSipExternalListeningPort requer a porta 5088

  - UcwaSipPrimaryListeningPort requer a porta 5089

Para obter detalhes e orientações adicionais sobre os requisitos de porta e protocolo para a descoberta automática, consulte [port SUMMARY-autodiscover in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).

</div>

<div>

## <a name="certificate-requirements"></a>Requisitos de certificado

Se você oferecer suporte à descoberta automática para clientes móveis do Lync, precisará modificar as listas de nomes alternativos da entidade em certificados para dar suporte a conexões seguras dos clientes móveis. Você precisa solicitar e atribuir novos certificados, adicionando as entradas de nome alternativo de entidade descritas nesta seção, para cada servidor front-end e diretor que executa o serviço de descoberta automática. A abordagem recomendada é também modificar as listas de nomes alternativos da entidade em certificados para seus proxies reversos. Você precisa adicionar entradas de nome alternativo de entidade para cada domínio SIP em sua organização.

A reemissão de certificados usando uma autoridade de certificação interna é normalmente um processo simples, mas a adição de múltiplas entradas de nome de entidade alternativo aos certificados públicos usados pelo proxy reverso pode ser cara. Se você tiver muitos domínios SIP, tornando a adição de nomes alternativos de entidade muito caras, é possível configurar o proxy reverso para fazer a solicitação de serviço de descoberta automática inicial pela porta 80 usando HTTP, em vez da porta 443 usando HTTPS (a configuração padrão). A solicitação é redirecionada para a porta 8080 no diretor ou pool de front-ends. Quando você publica a solicitação de serviço de descoberta automática inicial na porta 80, não é necessário alterar certificados para o proxy reverso, porque a solicitação usa HTTP em vez de HTTPS. Essa abordagem é suportada, mas não é recomendável.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Requisitos de IIS (Serviços de Informações da Internet)

Recomendamos que você use IIS 7,5, IIS 8,0 ou IIS 8,5 para mobilidade. O instalador do serviço de mobilidade define sinalizadores no ASP.NET para melhorar o desempenho. O IIS 7,5 é instalado por padrão no Windows Server 2008 R2, o IIS 8,0 é instalado no Windows Server 2012 e o IIS 8,5 é instalado no Windows Server 2012 R2. O instalador do serviço de mobilidade altera automaticamente as configurações do ASP.NET.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Requisitos do balanceador de carga de hardware

No balanceador de carga de hardware que suporta o pool de front-ends, os IPs virtuais (VIPs) dos serviços Web externos para o tráfego de serviços Web devem ser configurados para origem. A afinidade de origem ajuda a garantir que várias conexões de um único cliente sejam enviadas a um servidor para manter o estado da sessão. Para obter detalhes sobre os requisitos de afinidade, consulte [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

Se você planeja dar suporte a clientes móveis do Lync somente em sua rede Wi-Fi interna, configure os VIPS de serviços Web internos para origem, conforme descrito em VIPs de serviços Web externos. Nessa situação, você deve usar a afinidade\_de endereço de origem (ou TCP) para os VIPs de serviços Web internos no balanceador de carga de hardware. Para obter detalhes, consulte [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

</div>

<div>

## <a name="reverse-proxy-requirements"></a>Requisitos de proxy reverso

Se você oferecer suporte à descoberta automática para clientes móveis do Lync, precisará atualizar a regra de publicação atual da seguinte maneira:

  - Se você decidir atualizar as listas de nomes alternativos de entidade nos certificados de proxy reverso e usar HTTPS para a solicitação de serviço de descoberta automática inicial, deverá atualizar a regra de publicação na Web para o lyncdiscover. \<sipdomain\>. Normalmente, isso é combinado com a regra de publicação para a URL de serviços Web externos no pool de front-ends.

  - Se você decidir usar HTTP para a solicitação inicial do serviço de descoberta automática para que não seja necessário atualizar a lista de nomes alternativos de entidade nos certificados de proxy reverso, você deverá criar uma nova regra de publicação na Web para a porta HTTP/TCP 80, se ainda não existir um. Se uma regra para HTTP/TCP 80 já existir, você poderá atualizar essa regra para incluir o lyncdiscover. \<entrada\> sipdomain.

</div>

</div>

<span> </span>

</div>

</div>

</div>

