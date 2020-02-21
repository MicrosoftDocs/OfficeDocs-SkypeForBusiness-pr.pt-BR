---
title: 'Lync Server 2013: serviços de domínio do Active Directory para o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00038dce85a7461be37456d9dee263a71f60c113
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Serviços de domínio do Active Directory para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-13_

O serviços de domínio do Active Directory funciona como o serviço de diretório para redes Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Os serviços de domínio do Active Directory também servem como a base na qual a infraestrutura de segurança do Microsoft Lync Server 2013 é criada. O objetivo desta seção é descrever como o Lync Server 2013 usa os serviços de domínio do Active Directory para criar um ambiente confiável para mensagens instantâneas, conferências da Web, mídia e voz. Para obter detalhes sobre as extensões do Lync Server para os serviços de domínio do Active Directory e sobre como preparar seu ambiente para os serviços de domínio do Active Directory, consulte [preparação de serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) na documentação de implantação. Para obter detalhes sobre a função dos Serviços de Domínio Active Directory em redes do Windows Server, consulte a documentação da versão do sistema operacional que você está usando.

O Lync Server 2013 usa os serviços de domínio do Active Directory para armazenar:

  - Configurações globais que todos os servidores que executam o Lync Server 2013 em uma floresta exigem.

  - Informações de serviço que identificam as funções de todos os servidores que executam o Lync Server 2013 em uma floresta.

  - Algumas configurações de usuário.

<div>

## <a name="active-directory-infrastructure"></a>Infraestrutura do Active Directory

Os requisitos de infraestrutura do Active Directory incluem o seguinte:

  - Requisitos do sistema operacional para controladores de domínio

  - Requisitos de nível funcional de floresta e domínio

  - Requisitos de domínio do catálogo global

Para obter detalhes, consulte [Active Directory Infrastructure Requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) na documentação de implantação.

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Preparação dos Serviços de Domínio Active Directory

<div>


> [!NOTE]  
> Recomendamos que você implante as configurações globais no contêiner de Configuração em vez do contêiner do Sistema. Isso não melhora a segurança, mas pode resultar em melhorias de escalabilidade para algumas topologias dos Serviços de Domínio Active Directory. Se você estiver migrando do Microsoft Office Communications Server 2007 e tiver usado o contêiner de sistema, mas planejar usar o contêiner de configuração, você deve mover as configurações no contêiner do sistema antes de fazer preparativos de atualização. Para migrar as configurações do contêiner de sistema para o contêiner de configuração, confira ferramenta de migração de <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A>configurações globais do Office Communications Server 2007 em.



</div>

Ao implantar o Lync Server 2013, a primeira etapa é preparar os serviços de domínio do Active Directory. Preparar os serviços de domínio do Active Directory para o Lync Server 2013 consiste nas seguintes três etapas:

  - **Preparar Esquema**. Esta tarefa estende o esquema nos serviços de domínio do Active Directory para incluir classes e atributos específicos do Lync Server 2013. Para obter detalhes sobre como preparar o esquema, consulte [running Active Directory Schema Preparation no Lync Server 2013](lync-server-2013-running-schema-preparation.md) na documentação de implantação. Para obter mais informações, consulte [migração do Office Communications Server 2007 R2 para o Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

  - **Preparar a floresta**. Esta tarefa cria objetos e configurações globais no domínio raiz da floresta, juntamente com os grupos universais administrativos e de serviços que regulam o acesso a esses objetos e configurações. Para obter detalhes sobre como preparar a floresta, consulte [running Forest Preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) na documentação de implantação.

  - **Preparar Domínio**. Esta tarefa adiciona as ACEs (entradas de controle de acesso) a grupos universais que concedem permissões para hospedar e gerenciar usuários dentro do domínio. Essa tarefa deve ser concluída em todos os domínios em que você deseja implantar servidores que executam o Lync Server 2013 e todos os domínios onde seus usuários do Lync Server residem. Para obter detalhes sobre como preparar o domínio, consulte [running Domain Preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) na documentação de implantação.

Para obter uma visão geral do processo completo para preparar o Active Directory e os direitos e permissões necessários para executar cada etapa, consulte [Active Directory Infrastructure Requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) na documentação de implantação.

</div>

<div>

## <a name="universal-groups"></a>Grupos universais

Durante a preparação da floresta, o Lync Server 2013 cria vários grupos universais nos serviços de domínio do Active Directory que têm permissão para acessar e gerenciar configurações globais e serviços. Esses grupos universais incluem:

  - **Grupos administrativos**. Esses grupos definem as funções de administrador fundamentais para uma rede do Lync Server. Durante a preparação da floresta, esses grupos de administradores são adicionados aos grupos de infraestrutura do Lync Server.

  - **Grupos de serviço**. Esses grupos são contas de serviço necessárias para acessar vários serviços fornecidos pelo Lync Server.

  - **Grupos de infraestrutura**. Esses grupos fornecem permissão para acessar áreas específicas da infraestrutura do Lync Server. Eles funcionam como componentes de grupos administrativos e você não deve modificá-los ou adicionar usuários diretamente a eles. Durante a preparação da floresta, os grupos de serviços e de administração específicos são adicionados aos grupos de infraestrutura apropriados.

Para obter detalhes sobre os grupos universais específicos criados ao preparar o AD para o Lync Server, bem como os grupos de serviço e administração que são adicionados aos grupos de infraestrutura, confira [as alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) na documentação de implantação.

<div>


> [!NOTE]  
> O Lync Server 2013 oferece suporte aos grupos universais no Windows Server 2012 para servidores que executam o Lync Server 2013, bem como sistemas operacionais Windows Server 2003 para controladores de domínio. Os membros de grupos universais podem incluir outros grupos e contas de qualquer domínio na árvore ou floresta de domínios e podem receber permissões em qualquer domínio na árvore ou floresta de domínios. O suporte a grupos universais, combinado com a delegação de administrador, simplifica o gerenciamento de uma implantação do Lync Server. Por exemplo, não é necessário adicionar um domínio para outro para permitir que um administrador gerencie os dois.



</div>

</div>

<div>

## <a name="role-based-access-control"></a>Controle de Acesso Baseado em Função

Além de criar grupos universais de serviço e de administração e de adicionar grupos de serviços e de administração aos grupos universais apropriados, a preparação da floresta também cria grupos RBAC (controle de acesso baseado em função). Para obter detalhes sobre grupos de RBAC específicos criados pela preparação da floresta, confira [as alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) na documentação de implantação. Para obter mais informações sobre grupos RBAC, consulte [controle de acesso baseado em função (RBAC) para o Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>Entradas de Controle de Acesso (ACEs) e herança

A preparação de floresta cria ACEs particulares e públicas e adiciona as ACEs aos grupos universais criados. Ele cria ACEs privadas específicas no contêiner de configurações globais usado pelo Lync Server. Esse contêiner é usado apenas pelo Lync Server e está localizado no contêiner de configuração ou no contêiner de sistema no domínio raiz, dependendo de onde você armazena as configurações globais.

A etapa de preparação do domínio adiciona ACEs (entradas de controle de acesso) a grupos universais que concedem permissões para hospedar e gerenciar usuários dentro do domínio. A preparação de domínio cria ACEs na raiz do domínio e três contêineres internos: Usuários, Computadores e Controladores de Domínio.

Para obter detalhes sobre as ACEs públicas criadas e adicionadas pela preparação da floresta e pela preparação do domínio, confira [as alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) e [as alterações feitas pela preparação do domínio no Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) na documentação de implantação.

As organizações geralmente bloqueiam o AD DS (Serviços de Domínio Active Directory) para ajudar a atenuar os riscos de segurança. No entanto, um ambiente do Active Directory bloqueado pode limitar as permissões exigidas pelo Lync Server 2013. Isso pode incluir a remoção das ACEs de contêineres e OUs e a desabilitação da herança de permissões nos objetos User, Contact, InetOrgPerson ou Computer. Em um ambiente bloqueado do Active Directory, as permissões devem ser definidas manualmente em contêineres e UOs que necessitam deles. Para obter detalhes, consulte [preparação de serviços de domínio do Active Directory bloqueados no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) na documentação de implantação.

</div>

<div>

## <a name="server-information"></a>Informações do servidor

Durante a ativação, o Lync Server 2013 publica as informações do servidor nos três seguintes locais nos serviços de domínio do Active Directory:

  - Um ponto de conexão de serviço (SCP) em cada objeto de computador do Active Directory correspondente a um computador físico no qual o Lync Server 2013 está instalado.

  - Objetos de servidor criados no contêiner da classe **msRTCSIP-Pools**.

  - Servidores confiáveis especificados no construtor de topologias.

</div>

<div>

## <a name="service-connection-points"></a>Pontos de conexão de serviço

Cada objeto do Lync Server 2013 nos serviços de domínio do Active Directory tem um SCP chamado serviços RTC, que por sua vez contém vários atributos que identificam cada computador e especificam os serviços que ele fornece. Entre os atributos do SCP mais importantes estão *serviceDNSName*, *serviceDNSNameType*, *serviceClassname* e *serviceBindingInformation*. Os aplicativos de gerenciamento de ativos de terceiros podem recuperar informações do servidor em uma implantação consultando nesses e em outros atributos do SCP.

</div>

<div>

## <a name="active-directory-server-objects"></a>Objetos de servidor do Active Directory

Cada função de servidor do Lync Server 2013 tem um objeto Active Directory correspondente cujos atributos definem os serviços fornecidos por essa função. Além disso, quando um servidor Standard Edition é ativado ou quando um pool Enterprise Edition é criado, o Lync Server 2013 cria um novo objeto **msRTCSIP-pool** no contêiner **msRTCSIP-Pools** . A classe **msRTCSIP-Pool** especifica o FQDN (nome de domínio totalmente qualificado) do pool, juntamente com a associação entre os componentes de front-end e back-end do pool. (Um servidor Standard Edition é considerado um pool lógico cujos front-end e back-end são colocados em um único computador.)

</div>

<div>

## <a name="trusted-servers"></a>Servidores confiáveis

No Lync Server 2013, os servidores confiáveis são aqueles especificados quando você executa o construtor de topologias e publica sua topologia. A topologia publicada, incluindo todas as informações do servidor, é armazenada no repositório de Gerenciamento Central. Somente os servidores definidos no repositório de Gerenciamento Central são confiáveis. No Lync Server 2013, um servidor confiável é aquele que atende aos seguintes critérios:

  - O FQDN do servidor ocorre na topologia armazenada no repositório de Gerenciamento Central.

  - O servidor apresenta um certificado válido de uma CA confiável. Para obter detalhes, consulte [Certificate Infrastructure Requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).

Quando um dos seguintes critérios está ausente, o servidor não é confiável e a conexão com ele é recusada. Esse requisito duplo impede um possível ataque, embora improvável, em que um servidor não autorizado tenta assumir o FQDN do servidor válido.

Além disso, para habilitar o Microsoft Office Communications Server 2007 R2 e o Microsoft Office Communications Server 2007 implantações para se comunicar com os servidores do Lync Server 2013, o Lync Server 2013 cria contêineres durante a preparação da floresta para conter listas de servidores confiáveis para versões anteriores. A tabela a seguir descreve os contêineres criados para permitir a compatibilidade com implementações anteriores.

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>Listas de servidores confiáveis e seus contêineres do Active Directory para compatibilidade com versões anteriores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lista de servidores confiáveis</th>
<th>Contêiner do Active Directory</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidores Standard Edition e Servidores Fron-End do pool Enterprise</p></td>
<td><p>Serviço RTC/Configurações Globais</p></td>
</tr>
<tr class="even">
<td><p>Servidores de Conferência</p></td>
<td><p>Serviço RTC/MCUs confiáveis</p></td>
</tr>
<tr class="odd">
<td><p>Servidores de Web Components</p></td>
<td><p>Serviço RTC/TrustedWebComponentsServers</p></td>
</tr>
<tr class="even">
<td><p>Servidores de Mediação e Servidores do Communicator Web Access, Servidor de Aplicativos, Registrador com QoE, Serviço de Conferência A/V (além de servidores SIP de terceiros)</p></td>
<td><p>Serviço RTC/serviços confiáveis</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Proxy</p></td>
<td><p>O Lync Server 2013 não dá suporte à compatibilidade com versões anteriores para servidores proxy</p></td>
</tr>
</tbody>
</table>


Para dar suporte a servidores confiáveis de versões anteriores, você deve executar a ferramenta Best Practices Analyzer. Para obter detalhes sobre como executar o analisador de [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633)práticas recomendadas, consulte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

