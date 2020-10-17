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
ms.openlocfilehash: 3a1ff88b11c7d0ce007fc3bac38e7e3618771fb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514018"
---
# <a name="key-security-features-in-lync-server-2013"></a>Principais recursos de segurança no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-18_

O Lync Server 2013 inclui vários recursos de segurança, incluindo autenticação de servidor para servidor, controle de acesso baseado em função e armazenamento centralizado de dados de configuração.

Este artigo fornece uma visão geral de alto nível da segurança do Lync Server 2013.

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Principais recursos de segurança no Lync Server 2013

A segurança é um tópico muito amplo. A segurança alcança todos os recursos do Lync Server 2013, bem como os bancos de dados, serviços e hardware que compõem um ecossistema do Lync. Este artigo descreve alguns dos recursos no Lync Server 2013 em particular que são projetados para segurança.

<div>

## <a name="planning-and-design-tools"></a>Ferramentas de planejamento e design

O Lync Server 2013 fornece duas ferramentas para facilitar o planejamento e o design e reduzir a chance de configuração indefinida de componentes do Lync Server.

  - A **ferramenta de planejamento de topologia** automatiza grande parte do processo de design de topologia. Você pode exportar os resultados da ferramenta de planejamento para o construtor de topologias, que é a ferramenta necessária para instalar cada servidor que executa o Lync Server 2013.

  - O **Construtor de topologias** armazena todas as informações de configuração no repositório de gerenciamento central.

Para obter detalhes sobre essas ferramentas, consulte [Planning for Lync Server 2013](lync-server-2013-planning.md).

</div>

<div>

## <a name="central-management-store"></a>Central Management Store

No Lync Server 2013, os dados de configuração sobre servidores e serviços fazem parte do repositório de gerenciamento central. O repositório de gerenciamento central oferece um armazenamento robusto, esquematizado dos dados necessários para definir, configurar, manter, administrar, descrever e operar uma implantação do Lync Server. Também valida os dados para garantir a consistência da configuração. Todas as alterações feitas nesses dados de configuração acontecem no repositório de gerenciamento central, eliminando problemas de "fora de sincronização".

Cópias de somente leitura dos dados são replicadas a todos os servidores na topologia, incluindo Servidores de Borda e Aparelhos de Filia Persistente. A replicação é gerenciada por um serviço que, por padrão, é executado sob o contexto do serviço de Rede, reduzindo os direitos e permissões para os de um simples usuário no computador.

</div>

<div>

## <a name="server-to-server-authentication"></a>Autenticação de servidor para servidor

No Lync Server 2013, a autenticação pode ser configurada entre servidores usando o protocolo de autorização aberta (OAuth). Por exemplo, você pode configurar o Lync Server 2013 para autenticar com um servidor que esteja executando o Exchange Server 2013. Usando o protocolo OAuth, o Lync Server e o servidor do Exchange podem confiar um no outro. Isso fornece a capacidade de integrar os produtos de forma perfeita. Para obter detalhes, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Gerenciamento baseado no Windows PowerShell e interface de gerenciamento baseado na Web

O Lync Server 2013 fornece uma interface de gerenciamento poderosa, criada na interface de linha de comando do Windows PowerShell. Ela inclui cmdlets para o gerenciamento de segurança e os recursos de segurança do Windows PowerShell estão habilitados por padrão, de modo que os usuários não podem executar scripts com facilidade ou sem ter conhecimento. Isso significa que os padrões do software são definidos para ajudar automaticamente a maximizar a segurança e a reduzir os meios para ataques. Para obter detalhes sobre o suporte de gerenciamento do Windows PowerShell no Lync Server 2013, consulte [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="role-based-access-control-rbac"></a>Controle de acesso baseado em função (RBAC)

O Microsoft Lync Server 2013 fornece controle de acesso baseado em função (RBAC) para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança. É possível usar o RBAC para seguir o princípio de "privilégios mínimos", no qual os usuários recebem somente os direitos administrativos que seus trabalhos exigem. O Lync Server 2013 introduz a capacidade de criar uma nova função e também a capacidade de modificar uma função existente. Para obter detalhes, consulte [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>NAT (conversão de endereço de rede)

O Lync Server 2013 não oferece suporte ao uso de NAT (conversão de endereço de rede) na interface interna do servidor de borda, mas suporta a colocação da interface externa do serviço de borda de acesso, serviço de borda de Webconferência e serviço de borda A/V por trás de um roteador ou firewall que realiza a conversão de endereço de rede (NAT) para topologias de servidor de borda consolidada Vários servidores de borda atrás de um balanceador de carga de hardware não podem usar NAT. Se vários servidores de borda usarem NAT em suas interfaces externas, será necessário o balanceamento de carga DNS (sistema de nomes de domínio). Por sua vez, o uso do balanceamento de carga DNS permite reduzir o número de endereços IP públicos por servidor de borda em um pool de servidor de borda. Para obter detalhes, consulte[Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

<div>


> [!NOTE]  
> Se você federar com empresas que têm uma implantação do Microsoft Office Communications Server 2007 e precisar usar áudio/vídeo entre sua empresa e a empresa federada, os requisitos de porta serão aqueles para a versão mais antiga dos servidores de Borda implantados. Por exemplo, os intervalos de portas necessários para essas versões mais antigas devem ser abertos para ambas as empresas até que o parceiro federado atualize seus servidores de borda para o Lync Server 2013. A qualquer momento, os requisitos de porta podem ser revisados e reduzidos de acordo com a nova configuração.



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>Certificados simplificados para servidores de borda

O Assistente de Implantação pode preencher automaticamente os SNs (nomes de entidade) e os SANs (nomes de entidade alternativos), reduzindo a possibilidade de inclusão de entradas desnecessárias e possivelmente perigosas.

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>SDL (ciclo de vida de desenvolvimento de segurança) de computação confiável

O Lync Server 2013 foi projetado e desenvolvido em conformidade com o SDL (Security Development Lifecycle) de computação confiável da Microsoft, descrito em <https://go.microsoft.com/fwlink/?linkid=68761> .

  - **Confiável por design**     A primeira etapa na criação de um sistema de comunicação unificada mais segura era criar modelos de ameaças e testar cada recurso conforme ele foi criado. Além disso, a Microsoft realiza testes fora do comportamento projetado para encontrar vulnerabilidades de segurança resultantes de um comportamento de produto inesperado. Diversos aprimoramentos relacionados à segurança foram integrados ao processo e práticas de codificação. As ferramentas de tempo de compilação detectam estouros de buffer e outras possíveis ameaças de segurança antes que o código seja verificado no produto final. É claro que é impossível estar preparado para todas as ameaças de segurança desconhecidas. Nenhum sistema pode garantir a segurança completa. No entanto, como o desenvolvimento de produtos adotou princípios de design seguros desde o início, o Lync Server 2013 incorpora tecnologias de segurança padrão do setor como parte fundamental de sua arquitetura.

  - **Confiável por padrão**     Por padrão, as comunicações de rede no Lync Server 2013 são criptografadas. Como todos os servidores usam certificados e autenticação Kerberos, TLS, protocolo SRTP (Secure Real-Time Transport Protocol) e outras técnicas de criptografia padrão da indústria, incluindo criptografia AES (Advanced Encryption Standard) de 128 bits, praticamente todos os dados do Lync Server são protegidos na rede. Além disso, o controle de acesso baseado em função permite implantar servidores que executam o Lync Server 2013 de modo que cada função de servidor execute apenas os serviços e tenha apenas as permissões relacionadas a esses serviços, que são apropriadas para a função de servidor.

  - **Confiável por implantação**     Toda documentação do Lync Server 2013 inclui práticas recomendadas e recomendações para ajudá-lo a determinar e configurar os níveis de segurança ideais para sua implantação e avaliar os riscos de segurança da ativação de opções não padrão.

</div>

</div>

<span> </span>

</div>

</div>

</div>

