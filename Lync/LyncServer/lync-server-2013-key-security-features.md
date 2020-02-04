---
title: 'Lync Server 2013: principais recursos de segurança'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55d59a6978b90db82ccf899df90b05c739e71a57
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a>Recursos de segurança-chave no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-18_

O Lync Server 2013 inclui vários recursos de segurança, incluindo autenticação de servidor para servidor, controle de acesso baseado em função e armazenamento centralizado de dados de configuração.

Este artigo fornece uma visão geral de alto nível da segurança do Lync Server 2013.

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Recursos de segurança-chave no Lync Server 2013

Segurança é um tópico bastante amplo. A segurança é feita em cada recurso do Lync Server 2013, além de bancos de dados, serviços e hardware que compõem um ecossistema do Lync. Este artigo descreve alguns dos recursos do Lync Server 2013 em particular, projetados para segurança.

<div>

## <a name="planning-and-design-tools"></a>Ferramentas de Planejamento e Design

O Lync Server 2013 fornece duas ferramentas para facilitar o planejamento e o design e reduzir a chance de configuração de componentes do Lync Server.

  - A **ferramenta de planejamento de topologia** automatiza grande parte do processo de design da topologia. Você pode exportar os resultados da ferramenta de planejamento para o construtor de topologias, que é a ferramenta necessária para instalar cada servidor que executa o Lync Server 2013.

  - **O Construtor de Topologias** armazena todas as informações de configuração no repositório de Gerenciamento Central.

Para obter detalhes sobre essas ferramentas, consulte [planejando o Lync Server 2013](lync-server-2013-planning.md).

</div>

<div>

## <a name="central-management-store"></a>Repositório de Gerenciamento Central

No Lync Server 2013, os dados de configuração sobre servidores e serviços fazem parte do repositório de gerenciamento central. O repositório de gerenciamento central fornece um armazenamento robusto e schematized dos dados necessários para definir, configurar, manter, administrar, descrever e operar uma implantação do Lync Server. Ele também valida os dados para assegurar a consistência da configuração. Todas as alterações nestes dados de configuração acontecem nesse repositório, eliminando problemas de "dessincronização".

Cópias somente leitura dos dados são replicadas para todos os servidores na topologia, incluindo Servidores de borda e Aparelhos de Filial Persistente. A replicação é gerenciada por um serviço que, por definição, é executado sob um contexto de serviço de rede, fazendo com que os direitos e permissões sejam reduzidos aos de um usuário comum do computador.

</div>

<div>

## <a name="server-to-server-authentication"></a>Autenticação Servidor para Servidor

No Lync Server 2013, a autenticação pode ser configurada entre servidores usando o protocolo OAuth (autorização aberta). Por exemplo, você pode configurar o Lync Server 2013 para autenticar com um servidor que esteja executando o Exchange Server 2013. Usando o protocolo OAuth, o Lync Server e o Exchange Server podem confiar uns com os outros. Isso possibilita a integração perfeita dos produtos. Para obter detalhes, consulte [Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Gerenciamento baseado no Windows PowerShell e Interface de Gerenciamento baseada na Web

O Lync Server 2013 fornece uma interface de gerenciamento poderosa, baseada na interface de linha de comando do Windows PowerShell. Inclui cmdlets para gerenciamento de segurança e recursos de segurança do Windows Power Shell padrão, habilitados para que os usuários não executem scripts inadvertidamente. Isso significa que os padrões do software são definidos automaticamente para maximizar a segurança e reduzir possíveis ataques. Para obter detalhes sobre o suporte ao gerenciamento do Windows PowerShell no Lync Server 2013, consulte [Shell de gerenciamento do Lync server 2013](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="role-based-access-control-rbac"></a>Controle de Acesso Baseado em Função (RBAC)

O Microsoft Lync Server 2013 fornece controle de acesso baseado em função (RBAC) para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança. Você pode usar o RBAC para acompanhar o princípio de "privilégio mínimo", em que os usuários recebem somente os direitos administrativos que seus trabalhos exigem. O Lync Server 2013 introduz a capacidade de criar uma nova função e também a capacidade de modificar uma função existente. Para obter detalhes, consulte [planejando o controle de acesso baseado em função no Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>Conversão de Endereço de Rede (NAT)

O Lync Server 2013 não oferece suporte ao uso de NAT (conversão de endereços de rede) na interface interna do servidor de borda, mas oferece suporte à colocação da interface externa do serviço de borda de acesso, serviço de borda de Webconferência e serviço de borda A/V por trás de um roteador ou firewall que executa a conversão de endereços de rede Múltiplos Servidores de Borda ocultos sob um balanceador de carga de hardware não podem usar o NAT. O balanceador de carga do DNS (Domain Name System) é obrigatório se múltiplos Servidores de Borda usarem o NAT em suas interfaces externas. Por sua vez, o uso do balanceador de carga do DNS permite reduzir o número de endereços de IP públicos por Servidor de Borda em um pool de Servidores de Borda. Para obter detalhes, consulte[planejando o acesso de usuários externos no Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

<div>


> [!NOTE]  
> Se você federa com empresas em uma implantação da Microsoft Office Communications Server 2007 e precisa usar áudio/vídeo entre a sua empresa e a empresa federada, os requisitos de porta serão os da versão antiga do Servidor de Borda implantado. Por exemplo, os intervalos de porta necessários para essas versões mais antigas devem ser abertos para ambas as empresas até que o parceiro federado atualize seus servidores de borda para o Lync Server 2013. Neste momento, os requisitos de porta poderão ser revistos e reduzidos de acordo com a nova configuração.



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>Simplificar Certificados para Servidores de Borda

O Assistente de Implantação preenche nomes de identidade (SNs) e nomes de identidade alternativos (SANs) automaticamente, reduzindo possíveis inclusões desnecessárias e entradas potencialmente não seguras.

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>Ciclo de Vida do Desenvolvimento da Segurança de Computação Confiável (SDL)

O Lync Server 2013 foi projetado e desenvolvido em conformidade com o SDL (Microsoft Trustworthy Computing Security Lifecycle), descrito em <http://go.microsoft.com/fwlink/?linkid=68761>.

  - **Confiável por meio do design**   da primeira etapa na criação de um sistema de comunicação unificado mais seguro era criar modelos de ameaças e testar cada recurso conforme ele foi projetado. Além disso, a Microsoft executa testes de comportamento fora do esperado para encontrar vulnerabilidades na segurança resultantes de atitudes inesperadas do projeto. Os múltiplos aperfeiçoamentos relacionados à segurança foram criados dentro do código de processos e práticas. As ferramentas de construção em tempo detectam invasões de buffer e outras potenciais ameaças antes do código ser checado no produto final. Claro, é impossível detectar todas as ameaças de segurança desconhecidas. Nenhum sistema pode garantir segurança completa. No entanto, como o desenvolvimento de produto adotou princípios de design seguro desde o início, o Lync Server 2013 incorpora tecnologias de segurança padrão do setor como parte fundamental da arquitetura.

  - **Confiável por**   padrão, por padrão, as comunicações de rede no Lync Server 2013 são criptografadas. Como todos os servidores usam certificados e autenticação Kerberos, TLS, SSTP (Secure real-time Transport Protocol) e outras técnicas de criptografia padrão do setor, incluindo criptografia AES (padrão de criptografia avançada) de 128 bits, praticamente todos os lynces Os dados do servidor são protegidos na rede. Além disso, o controle de acesso baseado em função torna possível implantar servidores que executam o Lync Server 2013 para que cada função de servidor execute somente os serviços e tenha apenas as permissões relacionadas a esses serviços, que sejam apropriados para a função de servidor.

  - **Confiável**   para a implantação toda a documentação do Lync Server 2013 inclui práticas recomendadas e recomendações para ajudá-lo a determinar e configurar os níveis de segurança ideais para a sua implantação e avaliar os riscos de segurança da ativação de opções não padrão.

</div>

</div>

<span> </span>

</div>

</div>

</div>

