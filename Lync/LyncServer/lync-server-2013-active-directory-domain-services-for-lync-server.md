---
title: 'Lync Server 2013: serviços de domínio do Active Directory para o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a7dd0a5d5c6d8323abab3a8abfbc5f1025379e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Serviços de domínio do Active Directory para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-13_

O serviços de domínio Active Directory funciona como o serviço de diretório para redes Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Os serviços de domínio Active Directory também servem como a base na qual a infraestrutura de segurança do Microsoft Lync Server 2013 é criada. A finalidade desta seção é descrever como o Lync Server 2013 usa os serviços de domínio do Active Directory para criar um ambiente confiável para mensagens instantâneas, conferência na Web, mídia e voz. Para obter detalhes sobre as extensões do Lync Server para os serviços de domínio do Active Directory e sobre como preparar seu ambiente para os serviços de domínio Active Directory, consulte [preparando os serviços de domínio Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) na implantação documentação. Para obter detalhes sobre a função dos serviços de domínio do Active Directory nas redes do Windows Server, consulte a documentação da versão do sistema operacional que você está usando.

O Lync Server 2013 usa os serviços de domínio do Active Directory para armazenar:

  - Configurações globais que são necessárias para todos os servidores que executam o Lync Server 2013 em uma floresta.

  - Informações do serviço que identificam as funções de todos os servidores que executam o Lync Server 2013 em uma floresta.

  - Algumas configurações de usuário.

<div>

## <a name="active-directory-infrastructure"></a>Infraestrutura do Active Directory

Os requisitos de infraestrutura do Active Directory incluem o seguinte:

  - Requisitos do sistema operacional para controladores de domínio

  - Requisitos de níveis funcionais de domínio e de floresta

  - Requisitos de domínio do catálogo global

Para obter detalhes, consulte [requisitos de infraestrutura do Active Directory para o Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) na documentação de implantação.

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Preparação dos serviços de domínio Active Directory

<div>


> [!NOTE]  
> Recomendamos que você implante as configurações globais no contêiner de configuração, em vez do contêiner do sistema. Isso não melhora a segurança, mas pode resultar em melhorias de escalabilidade para algumas topologias de serviços de domínio Active Directory. Se estiver migrando do Microsoft Office Communications Server 2007 e tiver usado o contêiner do sistema, mas planejar o uso do contêiner de configuração, você deverá mover as configurações no contêiner do sistema antes de fazer os preparativos de atualização. Para migrar as configurações do contêiner do sistema para o contêiner de configuração, confira a ferramenta de migração <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>de configurações globais do Office Communications Server 2007 em.



</div>

Ao implantar o Lync Server 2013, a primeira etapa é preparar os serviços de domínio do Active Directory. A preparação dos serviços de domínio Active Directory para o Lync Server 2013 consiste nas três etapas a seguir:

  - **Preparar o esquema**. Essa tarefa estende o esquema nos serviços de domínio Active Directory para incluir classes e atributos específicos do Lync Server 2013. Para obter detalhes sobre como preparar o esquema, consulte [executando a preparação do esquema do Active Directory no Lync Server 2013](lync-server-2013-running-schema-preparation.md) na documentação de implantação. Para obter mais informações, consulte [migrar do Office Communications Server 2007 R2 para o Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

  - **Preparar a floresta**. Essa tarefa cria configurações e objetos globais no domínio raiz da floresta, juntamente com o serviço universal e os grupos administrativos que controlam o acesso a essas configurações e objetos. Para obter detalhes sobre como preparar a floresta, consulte [executando a preparação da floresta para o Lync Server 2013](lync-server-2013-running-forest-preparation.md) na documentação de implantação.

  - **Prepare o domínio**. Essa tarefa adiciona as entradas de controle de acesso (ACEs) necessárias a grupos universais que concedem permissões para hospedar e gerenciar usuários no domínio. Essa tarefa deve ser concluída em todos os domínios em que você deseja implantar servidores que executam o Lync Server 2013 e qualquer domínio onde os usuários do Lync Server estejam. Para obter detalhes sobre como preparar o domínio, consulte [executando a preparação do domínio para o Lync Server 2013](lync-server-2013-running-domain-preparation.md) na documentação de implantação.

Para obter uma visão geral do processo completo de preparação do Active Directory e dos direitos e permissões necessários para executar cada etapa, consulte [requisitos de infraestrutura do Active Directory para o Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) na documentação de implantação.

</div>

<div>

## <a name="universal-groups"></a>Grupos Universais

Durante a preparação da floresta, o Lync Server 2013 cria vários grupos universais dentro dos serviços de domínio do Active Directory que têm permissão para acessar e gerenciar configurações e serviços globais. Esses grupos universais incluem:

  - **Grupos Administrativos**. Esses grupos definem as funções de administrador fundamentais para uma rede do Lync Server. Durante a preparação da floresta, esses grupos de administradores são adicionados aos grupos de infraestrutura do Lync Server.

  - **Grupos de Serviços**. Esses grupos são contas de serviço que são necessárias para acessar vários serviços fornecidos pelo Lync Server.

  - **Grupos de infraestrutura**. Esses grupos fornecem permissão para acessar áreas específicas da infraestrutura do Lync Server. Eles funcionam como componentes dos grupos administrativos e você não deve modificá-los nem adicionar usuários diretamente a eles. Durante a preparação da floresta, grupos de serviços e de administração específicos são adicionados aos grupos de infraestrutura adequados.

Para obter detalhes sobre os grupos universais específicos criados ao preparar o AD para o Lync Server, bem como os grupos de serviços e administração que são adicionados aos grupos de infraestrutura, consulte [alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) na Documentação de implantação.

<div>


> [!NOTE]  
> O Lync Server 2013 dá suporte a grupos universais no Windows Server 2012 para servidores que executam o Lync Server 2013, bem como sistemas operacionais Windows Server 2003 para controladores de domínio. Os membros dos grupos universais podem incluir outros grupos e contas de qualquer domínio na árvore ou floresta de domínio e podem receber permissões em qualquer domínio na árvore ou floresta de domínio. O suporte a grupos universais, combinado com delegação de administrador, simplifica o gerenciamento de uma implantação do Lync Server. Por exemplo, não é necessário adicionar um domínio a outro para permitir que um administrador os gerencie.



</div>

</div>

<div>

## <a name="role-based-access-control"></a>Controle de Acesso Baseado em Função

Além de criar grupos de serviços e administração universais e de adicionar grupos de serviços e de administração aos grupos universais adequados, a preparação da floresta também cria grupos de Controle de acesso baseado em função (RBAC). Para obter detalhes sobre os grupos de RBAC específicos criados pela preparação da floresta, consulte [alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) na documentação de implantação. Para obter mais informações sobre grupos RBAC, consulte [controle de acesso baseado em função (RBAC) para o Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>Entradas de controle de acesso (ACEs) e Herança

A preparação da floresta cria ACEs privadas e públicas, adicionando ACEs nos grupos universais criados. Ele cria ACEs privadas específicas no contêiner de configurações globais usado pelo Lync Server. Esse contêiner é usado apenas pelo Lync Server e está localizado no contêiner de configuração ou no contêiner do sistema do domínio raiz, dependendo de onde você armazenou as configurações globais.

A etapa de preparação do domínio adiciona entradas de controle de acesso (ACEs) necessárias aos grupos universais que concedem permissões para hospedar e gerenciar usuários no domínio. A preparação do domínio cria ACEs no domínio raiz e três contêiners integrados: Usuário, Computadores e Controladores de Domínio.

Para obter detalhes sobre os ases públicos criados e adicionados pela preparação da floresta e pela preparação do domínio, confira [as alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) e [alterações feitas por preparação do domínio no Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) na implantação documentação.

Geralmente, as organizações bloqueiam os serviços de domínio Active Directory (AD DS) para ajudar a reduzir os riscos de segurança. No entanto, um ambiente do Active Directory bloqueado pode limitar as permissões exigidas pelo Lync Server 2013. Isso inclui remover ACEs dos contêineres e OUs e desabilitar a herança de permissões nos objetos de Usuário, Contato, InetOrgPerson ou Computador. Em um ambiente bloqueado do Active Directory, as permissões devem ser definidas manualmente em contêineres e UOs que exigem. Para obter detalhes, consulte [preparando os serviços de domínio do Active Directory bloqueados no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) na documentação de implantação.

</div>

<div>

## <a name="server-information"></a>Informações do servidor

Durante a ativação, o Lync Server 2013 publica as informações do servidor nos três seguintes locais nos serviços de domínio Active Directory:

  - Um SCP (ponto de conexão de serviço) em cada objeto de computador do Active Directory correspondente a um computador físico no qual o Lync Server 2013 está instalado.

  - Objetos de servidor criados no contêiner da classe **msRTCSIP-Pools**.

  - Servidores confiáveis especificados no construtor de topologias.

</div>

<div>

## <a name="service-connection-points"></a>Pontos de conexão de serviço

Cada objeto do Lync Server 2013 nos serviços de domínio Active Directory tem um SCP chamado serviços RTC, que, por sua vez, contém vários atributos que identificam cada computador e especificam os serviços que ele fornece. Dentre os atributos SCP mais importantes estão *serviceDNSName*, *serviceDNSNameType*, *serviceClassname* e *serviceBindingInformation*. Os aplicativos de gerenciamento de ativos de terceiros podem recuperar informações do servidor em uma implantação consultando esses e outros atributos SCP.

</div>

<div>

## <a name="active-directory-server-objects"></a>Objetos de servidor do Active Directory

Cada função de servidor do Lync Server 2013 tem um objeto do Active Directory correspondente cujos atributos definem os serviços fornecidos por essa função. Além disso, quando um servidor de edição padrão é ativado ou quando um pool da Enterprise Edition é criado, o Lync Server 2013 cria um novo objeto **msRTCSIP-pool** no contêiner **msRTCSIP-Pools** . A classe **msRTCSIP-Pool** especifica o nome de domínio totalmente qualificado (FQDN) do pool, juntamente com a associação entre os componentes de front-end e back-end do pool. (Um servidor Standard Edition é considerado um pool lógico cujas extremidades dianteiras e posteriores são posicionadas em um único computador.)

</div>

<div>

## <a name="trusted-servers"></a>Servidores confiáveis

No Lync Server 2013, os servidores confiáveis são aqueles especificados quando você executa o construtor de topologias e publica sua topologia. A topologia publicada, incluindo todas informações de servidor, é armazenada no Repositório de Gerenciamento Central. Apenas servidores definidos no Repositório de Gerenciamento Central são confiáveis. No Lync Server 2013, um servidor confiável é aquele que atende aos seguintes critérios:

  - O FQDN do servidor é apresentado na topologia armazenada no Repositório de gerenciamento central.

  - O servidor apresenta um certificado válido de uma CA confiável. Para obter detalhes, consulte [requisitos de infraestrutura de certificado para o Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).

Se algum desses critérios não for cumprido, o servidor não é confiável e a conexão será recusada. Este requisito duplo impede um possível, mesmo se improvável, ataque em que um servidor não autorizado tenta assumir um FQDN de um servidor válido.

Além disso, para habilitar implantações do Microsoft Office Communications Server 2007 R2 e do Microsoft Office Communications Server 2007 para se comunicar com servidores do Lync Server 2013, o Lync Server 2013 cria contêineres durante a preparação da floresta para listas de servidores confiáveis para versões anteriores. A tabela a seguir descreve os contêineres criados para permitir a compatibilidade com implantações anteriores.

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>Listas de servidores confiáveis e seus contêineres do Active Directory para compatibilidade com versões anteriores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lista de servidor confiável</th>
<th>Contêiner do Active Directory</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor Standard Edition e Servidor Front-End do Pool Enterprise</p></td>
<td><p>Configurações globais/Serviço RTC</p></td>
</tr>
<tr class="even">
<td><p>Servidores de Conferência</p></td>
<td><p>Serviço RTC/MCUs Confiáveis</p></td>
</tr>
<tr class="odd">
<td><p>Servidores de componentes da Web</p></td>
<td><p>Serviço RTC/TrustedWebComponentsServers</p></td>
</tr>
<tr class="even">
<td><p>Servidor de Mediação e Servidores do Communicator Web Access, Servidor de Aplicativo, Registrador do QoE, Serviço de Conferência A/V (também servidores SIP de terceiros)</p></td>
<td><p>Serviço RTC/Serviços confiáveis</p></td>
</tr>
<tr class="odd">
<td><p>Servidores proxy</p></td>
<td><p>O Lync Server 2013 não é compatível com a compatibilidade com versões anteriores para servidores proxy</p></td>
</tr>
</tbody>
</table>


Para dar suporte a servidores confiáveis de versões anteriores, você deve executar a ferramenta Analisador de práticas recomendadas. Para obter detalhes sobre como executar o analisador de [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)práticas recomendadas, consulte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

