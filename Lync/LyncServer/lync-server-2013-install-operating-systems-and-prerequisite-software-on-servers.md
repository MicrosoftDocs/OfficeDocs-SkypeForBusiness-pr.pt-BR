---
title: Instalar sistemas operacionais e software de pré-requisito nos servidores
description: Instalar sistemas operacionais e software de pré-requisito nos servidores.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bae9e57db9c2f1d3f3bde7ce9cc7071b73aa01d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574127"
---
# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Instalar sistemas operacionais e software de pré-requisito nos servidores do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-07-24_

Depois de configurar o hardware e a infraestrutura do sistema, você precisa instalar os sistemas operacionais Windows e as atualizações apropriadas, além de todos os outros programas necessários em cada servidor que estiver implantando. Isso inclui cada função de servidor do Lync Server 2013 e quaisquer servidores de infraestrutura adicionais ou servidores que executam o SQL Server necessários para sua implantação.

<div>


> [!NOTE]
> Esta seção descreve a instalação dos sistemas operacionais e softwares de pré-requisito para servidores internos. Se você estiver implantando servidores de borda para dar suporte ao acesso de usuário externo, também precisará instalar sistemas operacionais e software de pré-requisito para esses servidores, incluindo servidores de borda e servidores de proxy reverso. Para obter detalhes sobre como preparar servidores para dar suporte ao acesso de usuário externo, consulte <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">preparando para instalação de servidores na rede de perímetro do Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>Instalação dos sistemas operacionais Windows nos Servidores

Em cada servidor que você está implantando, instale o sistema operacional Windows apropriado da seguinte maneira:

  - **Servidores executando o Lync Server 2013**     Para obter detalhes sobre os requisitos do sistema operacional para servidores que executam o Lync Server 2013, consulte [Server and Tools Operating System support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

  - Servidores de banco de **dados**     Para obter detalhes sobre os requisitos do sistema operacional para servidores de banco de dados, incluindo o banco de dados back-end, banco de dados de arquivamento e banco de dados de monitoramento, consulte a documentação do SQL Server. Para o SQL Server 2012, confira o SQL Server 2012 Books Online em [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .

<div>


> [!NOTE]
> Se você estiver instalando o Lync Server 2013 no Windows Server &nbsp; 2008 &nbsp; R2 com SP1, deverá primeiro instalar a atualização descrita no artigo 2646886 de conhecimento da Microsoft, "correção: corrupção de pilha ocorre quando um módulo chama o método INSERTENTITYBODY no IIS 7,5", em <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 2646886</A>.<BR>Você também deve modificar o registro conforme descrito no artigo da base de conhecimento, as <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">identificações de evento 32402, 61045 são registradas nos servidores front-end do Lync Server 2013 instalados no Windows Server 2012 R2</A>.



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>Como instalar o Windows Update em servidores

Instale as seguintes atualizações do Windows Update em cada servidor:

  - **Atualização do Windows para servidores que executam o Lync Server 2013**     Para obter detalhes sobre as atualizações do Windows Update necessárias para servidores que executam o Lync Server 2013, consulte [Additional Software Requirements for Lync server 2013](lync-server-2013-additional-software-requirements.md) na documentação de planejamento.

  - Servidores de banco de **dados**     Para obter detalhes sobre as atualizações do Windows Update necessárias para servidores de banco de dados, incluindo o banco de dados back-end, banco de dados de arquivamento e banco de dados de monitoramento, consulte a documentação do SQL Server 2012. Para o SQL Server 2012, confira o SQL Server 2012 Books Online em [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>Instalação de outros softwares de pré-requisito em servidores

O Lync Server 2013 requer a instalação do seguinte software adicional nos servidores:

  - **Software de pré-requisito para servidores que executam o Lync Server 2013**     Os pré-requisitos de software adicionais para servidores que executam o Lync Server 2013 dependem da função de servidor que está sendo implantada. Para obter detalhes sobre os requisitos de software específicos para cada servidor, consulte [Additional Software Requirements for Lync server 2013](lync-server-2013-additional-software-requirements.md) na documentação de planejamento.

  - **Windows Identity Foundation**     O Lync Server 2013 requer a instalação do Windows Identity Foundation para dar suporte a cenários de autenticação de servidor para servidor. Para verificar se ele já foi instalado no seu computador, vá para o painel de controle, clique em **programas e recursos**, **Veja atualizações instaladas**e procure em **Microsoft Windows**. Para obter detalhes sobre a instalação do Windows Identity Foundation, consulte [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .

  - **Microsoft .NET Framework 4,5**     A edição de 64 bits do Microsoft .NET Framework 4,5 é necessária para o Lync Server 2013.

  - **Software de pré-requisito para servidores**     de banco de dados Para obter detalhes sobre a atualização do Windows necessária para servidores de banco de dados, incluindo o banco de dados back-end, banco de dados de arquivamento e banco de dados de monitoramento, consulte a documentação do SQL Server 2012 em [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .
    
    <div>
    

    > [!NOTE]
    > O Lync Server 2013 instala automaticamente o Microsoft SQL Server 2012 Express em cada servidor Standard Edition e cada servidor executando o Lync Server 2013 no qual o repositório de configuração local está localizado.

    
    </div>

  - **Tempo de execução**     do Windows Media Format Todos os servidores front-end e servidores Standard Edition onde a conferência será implantada deve ter o Windows Media Format Runtime instalado. O Tempo de Execução do Windows Media Format é necessário para executar arquivos de Áudio do Windows Media (.wma), que aplicativos de Estacionamento de Chamadas, Comunicados e Grupos de Resposta reproduzem para comunicados e música.
    
    <div>
    

    > [!NOTE]
    > Para o Windows Server 2012 e o Windows Server 2012 R2, o tempo de execução do Windows Media Format é instalado com o Microsoft Media Foundation.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Para o Windows Server &nbsp; 2008 e o Windows server &nbsp; 2008 &nbsp; R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows. É recomendável instalar a experiência da área de trabalho do Windows antes de instalar o Lync Server 2013. Se o Lync Server 2013 não localizar esse software no servidor, ele solicitará que você o instale e, em seguida, será necessário reiniciar o servidor para concluir a instalação.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

