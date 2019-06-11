---
title: 'Lync Server 2013: Requisitos técnicos para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac74f7e9e85829e500900e03d4b7cfedf89d1e0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Requisitos técnicos para mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Os usuários móveis encontram vários cenários de aplicativos móveis que exigem planejamento especial. Por exemplo, alguém pode começar a usar um aplicativo móvel enquanto estiver longe de trabalhar conectando-se pela rede 3G, alternar para a rede Wi-Fi corporativa quando chegar no trabalho e, em seguida, voltar para 3G quando sair do edifício. Você precisa planejar seu ambiente para dar suporte a transições de rede e garantir uma experiência de usuário consistente. Esta seção descreve os requisitos de infraestrutura que você deve ter para dar suporte a aplicativos móveis e descoberta automática de recursos de mobilidade.

<div>


> [!NOTE]  
> Embora os aplicativos móveis também possam se conectar a outros serviços do Lync Server 2013, a necessidade de enviar todas as solicitações da Web de aplicativo móvel para o mesmo nome de domínio totalmente qualificado (FQDN) da Web externa aplica-se somente ao serviço Lync Server 2013 Mobility. Outros serviços de mobilidade não exigem essa configuração.



</div>

A necessidade de afinidade de cookie em balanceadores de carga de hardware é reduzida drasticamente, e você substitui a afinidade TCP (Transmission Control Protocol) se estiver usando o Lync Mobile fornecido com o Lync Server 2013. A afinidade de cookie ainda pode ser usada, mas os serviços Web não precisam mais dele.

<div>


> [!IMPORTANT]  
> Todo o tráfego do serviço de mobilidade passa pelo proxy reverso, independentemente de onde o ponto de origem for — interno ou externo. No caso de um único proxy reverso ou de um farm de proxies invertidos ou um dispositivo que está fornecendo a função de proxy reverso, um problema pode ocorrer quando o tráfego interno está fazendo a saída por uma interface e tentando se fazer a ingresso imediatamente na mesma interface. Isso geralmente leva a uma violação de regra de segurança conhecida como falsificação de pacotes TCP ou apenas spoofing. <EM>Fixação de cabelo</EM> (o egresso e os ingressos imediatos de um pacote ou uma série de pacotes) devem ser permitidos para que a mobilidade funcione. Uma maneira de resolver esse problema é usar um proxy inverso que é separado do firewall (a regra de prevenção de spoofing sempre deve ser imposta no firewall para fins de segurança). O conecte pode ocorrer na interface externa do proxy reverso, em vez da interface externa do firewall. Você detecta a falsificação no firewall e relaxar a regra no proxy reverso, permitindo assim que o conecte que a mobilidade exija.<BR>Use o host DNS (sistema de nomes de domínio) ou os registros CNAME para definir o proxy inverso para o comportamento conecte (não o firewall), se possível.



</div>

O Lync Server 2013 oferece suporte a serviços de mobilidade para clientes móveis do Lync 2010 e Lync 2013. Os dois clientes usam o serviço de descoberta automática do Lync Server 2013 para localizar o ponto de entrada da mobilidade, mas são diferentes de qual serviço de mobilidade ele usa. O Lync 2010 Mobile usa o serviço de mobilidade conhecido como *MCX*, introduzido com a atualização cumulativa do Lync Server 2010: de novembro de 2011. Os clientes móveis do Lync 2013 usam a API da Web de comunicação unificada ou o *UCWA*, como provedor de serviços de mobilidade.

<div>

## <a name="internal-and-external-dns-configuration"></a>Configuração DNS interna e externa

Os serviços de mobilidade MCX (introduzidos com a atualização cumulativa para o Lync Server 2010: novembro de 2011) e UCWA (introduzidas nas atualizações cumulativas do Lync Server 2013: fevereiro de 2013) Use o DNS da mesma maneira.

Quando você usa a descoberta automática, os dispositivos móveis usam o DNS para localizar recursos. Durante a pesquisa de DNS, uma conexão é tentada primeiro para o FQDN associado ao registro DNS interno (lyncdiscoverinternal.\< nome\>de domínio interno). Se não for possível fazer uma conexão usando o registro DNS interno, será feita uma tentativa de conexão usando o registro DNS externo (lyncdiscover.\< sipdomain\>). Um dispositivo móvel interno à rede se conecta à URL interna do serviço de descoberta automática, e um dispositivo móvel externo à rede se conecta à URL externa do serviço de descoberta automática. As solicitações de descoberta automática externa passam pelo proxy reverso. O serviço descoberta automática do Lync Server 2013 retorna todas as URLs de serviços Web do pool primário do usuário, incluindo as URLs do serviço de mobilidade (MCX e UCWA). No entanto, tanto a URL do serviço de mobilidade interna quanto a URL do serviço de mobilidade externa são associadas ao FQDN de serviços Web externos. Portanto, não importa se um dispositivo móvel é interno ou externo à rede, o dispositivo sempre se conecta ao serviço de mobilidade do Lync Server 2013 externamente por meio do proxy reverso.

<div>


> [!NOTE]  
> É importante compreender que sua implantação pode consistir em vários namespaces distintos para uso interno e externo. O nome do seu domínio SIP pode ser diferente do nome do domínio de implantação interna. Por exemplo, seu domínio SIP pode ser <STRONG>contoso.com</STRONG>, enquanto sua implantação interna pode ser <STRONG>contoso.net</STRONG>. Os usuários que fizerem logon no Lync Server usarão o nome de domínio SIP, como <STRONG>John@contoso.com</STRONG>. Ao abordar os serviços Web externos (definidos no construtor de topologia como <STRONG>Serviços Web externos</STRONG>), o nome de domínio e o nome de domínio SIP serão consistentes, conforme definido no DNS. Ao abordar os serviços internos da Web (definidos no construtor de topologias como <STRONG>Serviços Web internos</STRONG>), o nome padrão dos serviços Web internos será o FQDN do servidor de front-end, do diretor de front-end, diretor ou do pool do diretor. Você tem a opção de substituir o nome interno dos serviços Web. Você deve usar o nome de domínio interno (e não o nome de domínio SIP) para serviços Web internos e definir o host DNS A (ou, para IPv6, AAAA) para refletir o nome substituído. Por exemplo, o FQDN de serviços Web internos padrão pode ser <STRONG>pool01.contoso.net</STRONG>. Um FQDN de serviços Web internos substituído pode ser <STRONG>webpool.contoso.net</STRONG>. A definição dos serviços Web dessa maneira ajuda a garantir que a localidade interna e externa dos serviços, e não a localidade do usuário que os está usando, é observada.<BR>No entanto, como os serviços Web são definidos no construtor de topologias e o nome interno dos serviços Web podem ser substituídos, contanto que o nome dos serviços Web resultantes, o certificado que o valida e os registros DNS que os definem, sejam consistentes, você pode definir o serviços internos da Web com qualquer nome de domínio, incluindo o nome de domínio SIP, que você deseja. Em última análise, a resolução do nome para o endereço IP é determinada pelos registros do host DNS e um namespace consistente.<BR>Para os fins deste tópico e os exemplos, o nome de domínio interno é usado para ilustrar a topologia e as definições de DNS.



</div>

O diagrama a seguir ilustra o fluxo de solicitações da Web de aplicativo móvel para o serviço de mobilidade e para o serviço de descoberta automática ao usar uma configuração DNS interna e externa.

**Fluxo de serviço de mobilidade usando a descoberta automática**

![cdb96424-96f2-4ABF-88d7-1d32d1010ffd] (images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4ABF-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> O diagrama ilustra serviços Web genéricos. Um diretório virtual chamado Mobility representa os serviços de mobilidade MCX e/ou UCWA. Se você não aplicou as atualizações cumulativas do Lync Server 2013:2013 de fevereiro, pode ou não ter o diretório virtual Ucwa definido nos seus serviços Web internos e externos. Você terá uma descoberta automática de diretório virtual e poderá ter um diretório virtual MCX.<BR>A descoberta automática e a descoberta de serviços funcionam da mesma maneira, independentemente da tecnologia de serviços de mobilidade que você tenha implantado.



</div>

Para dar suporte a usuários móveis dentro e fora da rede corporativa, os FQDNs da Web internos e externos devem atender a alguns pré-requisitos. Além disso, talvez seja necessário atender a outros requisitos, dependendo dos recursos que você optar por implementar:

  - Novos registros DNS, CNAME ou A (host, se IPv6, AAAA) para descoberta automática.

  - Nova regra de firewall, se você quiser dar suporte a notificações de envio pela sua rede Wi-Fi.

  - Nomes alternativos de assunto em certificados de servidor internos e certificados de proxy reverso para descoberta automática.

  - Configuração do balanceador de carga de hardware do front-end altera a afinidade de origem.

Sua topologia deve atender aos seguintes requisitos para dar suporte ao serviço de mobilidade e ao serviço de descoberta automática:

  - O FQDN da Web interna do pool de front-end deve ser diferente do FQDN da Web externa do pool de front-end.

  - O FQDN interno da Web só deve ser resolvido e estar acessível dentro da rede corporativa.

  - O FQDN da Web externo só deve ser resolvido para a Internet e estar acessível para ser acessado.

  - Para um usuário que está dentro da rede corporativa, a URL do serviço de mobilidade deve ser endereçada ao FQDN da Web externa. Esse requisito é para o serviço de mobilidade e aplica-se somente a essa URL.

  - Para um usuário que está fora da rede corporativa, a solicitação deve acessar o FQDN da Web externo do pool ou do diretor de front-end.

Se você oferecer suporte à descoberta automática, será necessário criar os seguintes registros DNS para cada domínio SIP:

  - Um registro DNS interno para dar suporte a usuários móveis que se conectam dentro da rede da sua organização.

  - Um registro DNS externo ou público para dar suporte a usuários móveis que se conectam à Internet.

A URL de descoberta automática interna não deve ser endereçável de fora da rede. A URL de descoberta automática externa não deve ser endereçada dentro da sua rede. No entanto, se você não puder atender a esse requisito para a URL externa, o cliente móvel provavelmente não será afetado, porque a URL interna sempre é sempre tentada primeiro.

Os registros DNS podem ser registros CNAME ou registros (host, se IPv6, AAAA).

<div>


> [!NOTE]  
> Os clientes de dispositivos móveis não dão suporte a vários certificados SSL (Secure Sockets Layer) de domínios diferentes. Portanto, não há suporte para o redirecionamento CNAME para domínios diferentes em HTTPS. Por exemplo, um registro CNAME de DNS para lyncdiscover.contoso.com que redireciona para um endereço de director.contoso.net não é compatível com HTTPS. Em uma topologia como essa, um cliente de dispositivo móvel precisa usar HTTP para a primeira solicitação, para que o redirecionamento CNAME seja resolvido por HTTP. Solicitações subsequentes e, em seguida, use HTTPS. Para dar suporte a esse cenário, você precisa configurar seu proxy reverso com uma regra de publicação na Web para a porta 80 (HTTP). Para obter detalhes, consulte "criar uma regra de publicação na Web para a porta 80" em Configurando <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">o proxy reverso para a mobilidade no Lync Server 2013</A>.<BR>O redirecionamento CNAME para o mesmo domínio é compatível com HTTPS. Nesse caso, o certificado do domínio de destino abrange o domínio de origem.



</div>

Para obter detalhes sobre os registros DNS necessários para seu cenário, consulte [Resumo de DNS-descoberta automática no Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).

</div>

<div>

## <a name="port-and-firewall-requirements"></a>Requisitos de portabilidade e firewall

Se você oferecer suporte a notificações por push e desejar que os dispositivos móveis da Apple recebam notificações por push na sua rede Wi-Fi, também será necessário abrir a porta 5223 na rede Wi-Fi da sua empresa. A porta 5223 é uma porta TCP de saída usada pelo serviço de notificação por push da Apple (APNS). O dispositivo móvel inicia a conexão. Para obter detalhes, [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) consulte.

<div>


> [!WARNING]  
> Um dispositivo Apple que usa o cliente móvel Lync 2013 não requer notificações por push.



</div>

Observe que, se um usuário estiver hospedado em um aparelho de ramificação sobreviventes (SBA), as seguintes portas serão necessárias:

  - UcwaSipExternalListeningPort requer a porta 5088

  - UcwaSipPrimaryListeningPort requer a porta 5089

Para obter detalhes adicionais e obter diretrizes sobre requisitos de protocolo e porta para descoberta automática, consulte [Resumo de porta-descoberta automática no Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).

</div>

<div>

## <a name="certificate-requirements"></a>Requisitos de certificado

Se você oferecer suporte à descoberta automática para clientes móveis do Lync, será necessário modificar as listas de nomes alternativos de entidades nos certificados para dar suporte a conexões seguras de clientes móveis. Você precisa solicitar e atribuir novos certificados, adicionar as entradas de nome alternativo para o assunto descritas nesta seção para cada servidor e diretor de front-end que executa o serviço descoberta automática. A abordagem recomendada é também modificar as listas de nomes alternativos de entidades em certificados para seus proxies invertidos. Você precisa adicionar entradas de nomes alternativos de entidades para cada domínio SIP em sua organização.

A emissão de certificados por meio de uma autoridade de certificação interna geralmente é um processo simples, mas adicionar várias entradas de nome alternativo à entidade para certificados públicos usados pelo proxy reverso pode ser caro. Se você tiver muitos domínios SIP, o que faz com que a adição dos nomes alternativos de assunto seja muito cara, você pode configurar o proxy reverso para fazer a solicitação inicial de serviço de descoberta automática pela porta 80 usando HTTP, em vez da porta 443 usando HTTPS (a configuração padrão). A solicitação será redirecionada para a porta 8080 no diretor ou no pool de front-ends. Quando você publica a solicitação de serviço de descoberta automática inicial na porta 80, não é necessário alterar certificados para o proxy reverso, porque a solicitação usa HTTP em vez de HTTPS. Essa abordagem tem suporte, mas não é recomendável.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Requisitos dos serviços de informações da Internet (IIS)

Recomendamos que você use o IIS 7,5, o IIS 8,0 ou o IIS 8,5 para mobilidade. O instalador do serviço de mobilidade define sinalizadores no ASP.NET para melhorar o desempenho. O IIS 7,5 é instalado por padrão no Windows Server 2008 R2, o IIS 8,0 está instalado no Windows Server 2012, e o IIS 8,5 está instalado no Windows Server 2012 R2. O instalador do serviço de mobilidade altera automaticamente as configurações do ASP.NET.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Requisitos do Balanceador de Carga de Hardware

No balanceador de carga de hardware que oferece suporte ao pool de front-end, os IPs virtuais (VIPs) de serviços Web externos para tráfego de serviços Web devem ser configurados para a fonte. A afinidade de origem ajuda a garantir que várias conexões de um único cliente sejam enviadas para um servidor para manter o estado da sessão. Para obter detalhes sobre requisitos de afinidade, consulte [requisitos de balanceamento de carga para o Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

Se você planeja dar suporte a clientes móveis do Lync apenas em sua rede Wi-Fi interna, configure os VIPS de serviços Web internos para a origem, conforme descrito para VIPs de serviços Web externos. Nessa situação, você deve usar a afinidade\_de endereço de origem (ou TCP) para os VIPs de serviços Web internos no balanceador de carga de hardware. Para obter detalhes, consulte [requisitos de balanceamento de carga para o Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

</div>

<div>

## <a name="reverse-proxy-requirements"></a>Requisitos de proxy reverso

Se você oferecer suporte à descoberta automática para clientes móveis do Lync, será necessário atualizar a regra de publicação atual da seguinte maneira:

  - Se você decidir atualizar as listas de nomes alternativos de entidades nos certificados de proxy reverso e usar HTTPS para a solicitação de serviço de descoberta automática inicial, será necessário atualizar a regra de publicação da Web para lyncdiscover. \<sipdomain\>. Geralmente, isso é combinado com a regra de publicação para a URL de serviços Web externos no pool de front-ends.

  - Se você decidir usar HTTP para a solicitação de serviço de descoberta automática inicial para não precisar atualizar a lista de nomes alternativos de entidades nos certificados de proxy reverso, será necessário criar uma nova regra de publicação na Web para a porta HTTP/TCP 80, caso ainda não exista uma. Se uma regra para HTTP/TCP 80 já existir, você poderá atualizar essa regra para incluir o lyncdiscover. \<entrada\> sipdomain.

</div>

</div>

<span> </span>

</div>

</div>

</div>

