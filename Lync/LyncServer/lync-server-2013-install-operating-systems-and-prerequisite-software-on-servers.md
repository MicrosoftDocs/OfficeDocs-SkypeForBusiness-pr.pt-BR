---
title: Instalar sistemas operacionais e software de pré-requisito nos servidores
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
ms.openlocfilehash: 8c41147d33dce792f88b30f72b36201ddb6c7d62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Instalar sistemas operacionais e software de pré-requisito nos servidores para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-07-24_

Depois de configurar a infraestrutura de hardware e do sistema, você precisa instalar os sistemas operacionais e atualizações apropriados do Windows, além de todos os outros softwares de pré-requisito em cada servidor que estiver implantando. Isso inclui cada função de servidor do Lync Server 2013 e qualquer servidor de infraestrutura adicional ou servidores que executam o SQL Server necessários para sua implantação.

<div>


> [!NOTE]
> Esta seção descreve a instalação de sistemas operacionais e software de pré-requisito para servidores internos. Se você estiver implantando servidores de borda para dar suporte a acesso externo a usuários, também precisará instalar sistemas operacionais e software de pré-requisito para esses servidores, incluindo servidores de borda e servidores proxy reverso. Para obter detalhes sobre como preparar servidores para dar suporte a acesso externo a usuários, consulte Preparando-se <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">para a instalação de servidores na rede de perímetro do Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>Instalar sistemas operacionais Windows em servidores

Em cada servidor que você está implantando, instale o sistema operacional do Windows apropriado da seguinte maneira:

  - **Servidores que executam o Lync Server 2013**   para obter detalhes sobre os requisitos do sistema operacional para servidores que executam o Lync Server 2013, consulte [suporte ao sistema operacional do servidor e ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

  - **Servidores de banco de dados**   para obter detalhes sobre os requisitos de sistema operacional para servidores de banco de dados, incluindo o banco de dados back-end, o banco de dados de arquivamento e o banco de dados de monitoramento, consulte a documentação Para o SQL Server 2012, consulte os manuais online do SQL Server [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)2012 em.

<div>


> [!NOTE]
> Se você estiver instalando o Lync Server 2013 no&nbsp;Windows&nbsp;Server 2008 R2 com SP1, deve primeiro instalar a atualização descrita no artigo da base de dados de conhecimento Microsoft 2646886, "correção: a corrupção de pilha ocorre quando um módulo chama o método InsertEntityBody no IIS 7,5", em <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.<BR>Você também deve modificar o registro conforme descrito no artigo da base de conhecimento, os <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">IDs de evento 32402, 61045 são registrados nos servidores front-end do Lync server 2013 instalados no Windows Server 2012 R2</A>.



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>Instalar o Windows Update em servidores

Instale as seguintes atualizações do Windows Update em cada servidor:

  - **Windows Update para servidores que executam o Lync Server 2013**   para obter detalhes sobre as atualizações do Windows Update necessárias para servidores que executam o Lync Server 2013, consulte [requisitos de software adicionais para o Lync Server 2013](lync-server-2013-additional-software-requirements.md) na documentação de planejamento.

  - **Servidores de banco de dados**   para obter detalhes sobre as atualizações do Windows Update necessárias para servidores de banco de dados, incluindo o banco de dados back-end, o banco de dados de arquivamento e o banco de dados de monitoramento, consulte a documentação do SQL Server 2012. Para o SQL Server 2012, consulte os manuais online do SQL Server [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)2012 em.

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>Instalar outro software de pré-requisito em servidores

O Lync Server 2013 requer a instalação do seguinte software adicional nos servidores:

  - **Software de pré-requisito para servidores que executam o Lync Server 2013**   os pré-requisitos de software adicionais para servidores que executam o Lync Server 2013 dependem da função do servidor que está sendo implantado. Para obter detalhes sobre os requisitos de software específicos para cada servidor, consulte [requisitos adicionais de software para o Lync server 2013](lync-server-2013-additional-software-requirements.md) na documentação de planejamento.

  - ****   O Lync Server do Windows Identity Foundation 2013 exige a instalação do Windows Identity Foundation para dar suporte a cenários de autenticação de servidor para servidor. Para verificar se ele já foi instalado no computador, vá para o painel de controle, clique em **programas e recursos**, **Veja atualizações instaladas**e procure em **Microsoft Windows**. Para obter detalhes sobre como instalar o Windows Identity [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.

  - **Microsoft .NET Framework 4,5**   a edição de 64 bits do Microsoft .NET Framework 4,5 é necessária para o Lync Server 2013.

  - **Software de pré-requisito para servidores**   de banco de dados para obter detalhes sobre a atualização do Windows necessária para servidores de banco de dados, incluindo o banco de dados back-end, banco de dados de [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)arquivamento e banco de dados monitoramento, consulte a documentação do SQL Server 2012 em.
    
    <div>
    

    > [!NOTE]
    > O Lync Server 2013 instala automaticamente o Microsoft SQL Server 2012 Express em cada servidor Standard Edition e cada servidor que executa o Lync Server 2013 no qual o repositório de configuração local está localizado.

    
    </div>

  - **Tempo de execução**   do formato do Windows Media todos os servidores front-end e servidores Standard Edition em que a conferência será implantada deve ter o tempo de execução do Windows Media Format instalado. O tempo de execução do Windows Media Format é necessário para executar os arquivos de áudio do Windows Media (. WMA) que os aplicativos de estacionamento de chamada, anúncio e resposta são reproduzidos para anúncios e músicas.
    
    <div>
    

    > [!NOTE]
    > Para Windows Server 2012 e Windows Server 2012 R2, o tempo de execução do Windows Media Format é instalado com o Microsoft Media Foundation.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Para o Windows&nbsp;Server 2008 e o&nbsp;Windows&nbsp;Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows. É recomendável instalar a experiência da área de trabalho do Windows antes de instalar o Lync Server 2013. Se o Lync Server 2013 não encontrar esse software no servidor, ele solicitará que você o instale e, em seguida, deverá reiniciar o servidor para concluir a instalação.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

