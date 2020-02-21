---
title: 'Lync Server 2013: ferramentas administrativas do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27a7567fa467f8e152f4b6a61b06600a127607d7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Ferramentas administrativas do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Este tópico descreve as ferramentas administrativas do Lync Server 2013.

As ferramentas administrativas são instaladas por padrão em cada servidor do Lync Server. Além disso, você pode instalar as ferramentas administrativas em outros computadores, tais como consoles administrativos dedicados. Para obter os procedimentos para instalar as ferramentas administrativas, consulte [install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md). Para obter os procedimentos para abrir as ferramentas para executar tarefas de gerenciamento, consulte [Open Lync Server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

Certifique-se de revisar os requisitos de direitos de infra-estrutura, sistema operacional, software e administrador antes de instalar ou usar as ferramentas administrativas do Lync Server. Para obter detalhes sobre os requisitos de infraestrutura, consulte [Administrative Tools Infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Para obter detalhes sobre os requisitos de sistema operacional e software para instalar as ferramentas administrativas do Lync Server, consulte [Server and Tools Operating System support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional Software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md)e [suporte e requisitos adicionais do servidor no Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). As permissões e os direitos de usuário necessários para instalar e usar as ferramentas são descritos em [direitos e permissões de administrador necessários para a instalação e administração do Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

As ferramentas administrativas consistem no seguinte:

  - **Assistente de implantação do Lync Server**   use para implantar o Lync Server e instalar todas as ferramentas administrativas.

  - **O Construtor**   de topologias do Lync Server usa para definir componentes em sua implantação.

  - **Painel de controle do Lync Server**   use para o gerenciamento contínuo da sua implantação usando uma interface baseada na Web.

  - **Shell de gerenciamento do Lync Server**   use para o gerenciamento contínuo da sua implantação usando a linha de comando.

  - **A ferramenta**   de registro em log do Lync Server é usada para solucionar problemas em sua implantação.

  - **O serviço**   de registro em log centralizado coleta logs e rastreamento de arquivos de um computador, pool, site ou global. Selecione e defina cenários que contenham provedores, sinalizadores e níveis de rastreamento. O registro em log é coletado, agregado e exibido com ferramentas como qualquer ferramenta baseada em texto ou Snooper. exe.

Você pode gerenciar sua implantação usando principalmente o construtor de topologias e o painel de controle do Lync Server.

<div>

## <a name="deployment-wizard"></a>Assistente de Implantação

Você deve usar o assistente de implantação do Lync Server incluído na mídia de instalação para instalar todas as ferramentas administrativas em um computador em que você ainda não tenha instalado o Lync Server. Durante o processo de instalação das ferramentas administrativas, o assistente de implantação do Lync Server é instalado localmente junto com outras ferramentas para que você possa usá-lo posteriormente para instalar arquivos para componentes adicionais ou remover arquivos de componentes que não deseja no computador.

Para obter detalhes sobre como executar o assistente de implantação do Lync Server pela primeira vez na mídia de instalação do Lync Server, consulte [install Lync server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).

</div>

<div>

## <a name="topology-builder"></a>Construtor de Topologias

Para obter detalhes sobre as tarefas de implantação que você pode executar usando o construtor de topologias, consulte a documentação de implantação de cada função de servidor.

</div>

<div>

## <a name="lync-server-control-panel"></a>Painel de controle do Lync Server

Você pode usar o painel de controle do Lync Server 2013 para executar a maioria das tarefas administrativas necessárias para gerenciar e manter o Lync Server 2013. O painel de controle do Lync Server oferece uma interface gráfica do usuário (GUI) para gerenciar a configuração dos servidores que executam o Lync Server, além dos usuários, clientes e dispositivos da sua organização. O Shell de gerenciamento do Lync Server usa o painel de controle do Lync Server como o mecanismo subjacente para executar a configuração do Lync Server.

O painel de controle do Lync Server é instalado automaticamente em todos os servidores front-end do Lync Server ou Standard Edition. Nesta versão, os Servidores de Borda são administrados remotamente. Você também pode instalar o painel de controle do Lync Server em outro computador, como um console de gerenciamento do qual você deseja gerenciar centralmente o Lync Server. Para obter detalhes, consulte [install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Para definir as configurações usando o painel de controle do Lync Server, você deve estar conectado usando uma conta atribuída à função CsAdministrator. Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Lync Server 2013, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync server 2013</A>.</P>
> <LI>
> <P>Para definir as configurações usando o painel de controle do Lync Server, você também deve usar um computador com uma resolução de tela mínima de 1024 x 768.</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Shell de Gerenciamento do Lync Server

No Lync Server, o Shell de gerenciamento do Lync Server fornece um novo método de administração e gerenciamento. O Shell de gerenciamento do Lync Server é uma interface de gerenciamento poderosa, criada na interface de linha de comando do Windows PowerShell, que inclui um conjunto abrangente de cmdlets específicos para o Lync Server. Com o Shell de gerenciamento do Lync Server, você obtém um conjunto avançado de controles de configuração e automação. O construtor de topologias e o painel de controle do Lync Server implementam subconjuntos desses cmdlets para dar suporte ao gerenciamento do Lync Server. O Shell de gerenciamento do Lync Server inclui cmdlets para todas as tarefas de administração do Lync Server e você pode usar os cmdlets individualmente para gerenciar sua implantação. Para obter detalhes, consulte a documentação do [Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md) ou a ajuda de linha de comando para cada cmdlet.

</div>

<div>

## <a name="logging-tool"></a>Ferramenta de Log

A ferramenta de registro em log do Lync Server facilita a solução de problemas ao capturar informações de log e rastreamento do produto enquanto o produto está em execução. Você pode usar a ferramenta para executar sessões de depuração em qualquer função de servidor do Lync Server. Para obter detalhes sobre a ferramenta de registro em log, consulte a documentação da ferramenta de registro em log [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265)do Lync Server 2010 na biblioteca do TechNet em.

<div>


> [!IMPORTANT]  
> O serviço de registro em log centralizado é recomendado para todas as coletas de log sobre a ferramenta de log do Lync Server em todas as circunstâncias. A ferramenta de log do Lync Server ainda funcionará, mas interferirá ou será renderizada principalmente se o serviço de registro em log centralizado já estiver em execução. Você deve usar somente o serviço de registro em log centralizado ou a ferramenta de log do Lync Server, mas nunca simultaneamente. Para obter mais informações sobre o serviço de registro em log centralizado e por que você deve usá-lo exclusivamente, consulte <A href="lync-server-2013-using-the-centralized-logging-service.md">usando o serviço de registro em log centralizado no Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Requisitos de infraestrutura de ferramentas administrativas no Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Suporte a sistemas operacionais de servidor e de ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Requisitos de software de ferramentas administrativas no Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

  - [Direitos e permissões de administrador necessários para a instalação e administração do Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Requisitos para publicar uma topologia no Lync Server 2013](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Instalar ferramentas administrativas do Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Abrir as ferramentas administrativas do Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Resolver problemas do painel de controle do Lync Server 2013](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Usando o serviço de registro em log centralizado no Lync Server 2013](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

