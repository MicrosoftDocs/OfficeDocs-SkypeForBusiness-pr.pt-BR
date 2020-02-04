---
title: 'Lync Server 2013: Requisitos adicionais de software'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc650b4c427640398af1748e86c7bca9d76c703d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Requisitos adicionais de software para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-12-08_

Além dos requisitos de hardware e sistema operacional das plataformas do servidor, o Lync Server 2013 requer a instalação de software adicional nos servidores que você implantar.

<div>


> [!NOTE]  
> Para obter detalhes sobre os requisitos da plataforma para servidores que executam o Lync Server, consulte <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware do servidor para o Lync server 2013</A> e <A href="lync-server-2013-server-and-tools-operating-system-support.md">servidor e ferramentas, suporte ao sistema operacional do Lync Server 2013</A>. Para obter detalhes sobre os requisitos do sistema para computadores e dispositivos cliente, consulte <A href="lync-server-2013-planning-for-clients-and-devices.md">planejando para clientes e dispositivos no Lync Server 2013</A> na documentação de planejamento. Para obter detalhes sobre os requisitos de software para ferramentas administrativas, consulte <A href="lync-server-2013-administrative-tools-software-requirements.md">requisitos de software para ferramentas administrativas no Lync Server 2013</A>.



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>Software adicional necessário para todas as funções de servidor interno

Esta seção lista o software necessário em todas as funções de servidor interno, que são todas as funções de servidor do Lync Server, exceto para o servidor de borda. Os requisitos para os servidores de borda e os pools de bordas são listados mais adiante neste tópico em **software adicional para servidores de borda**.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Cada servidor executando o Lync Server 2013 deve ter a versão correta do Windows PowerShell 3,0 instalada. Para obter detalhes, consulte [instalando o Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft.NET Framework 4.5

O Lync Server requer o Microsoft .NET Framework 4,5 em todas as funções de servidor interno e em qualquer computador no qual você executará as ferramentas administrativas do Lync Server ou o Microsoft Lync Server 2013, ferramenta de planejamento. Para o Lync Server 2013, você deve instalar manualmente a edição de 64 bits do Microsoft .NET Framework 4,5 no servidor antes de instalar o Lync Server 2013. Para instalá-lo manualmente, baixe a estrutura do Microsoft .NET 4,5 a partir do centro de download da Microsoft em[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Instalando o Microsoft .NET Framework 4,5 em servidores que executam o Windows Server 2012

Ao instalar o Microsoft .NET Framework 4,5 em servidores que executarão o Lync Server 2013 e o Windows Server 2012, você deve executar uma etapa adicional. Após instalar o .NET Framework 4,5, use o Gerenciador de servidores para instalar a ativação HTTP.

**Para instalar a ativação HTTP do .NET 4,5 no Windows Server 2012**

1.  No menu **Iniciar** , clique em **programas**e, em seguida, clique em **Ferramentas administrativas**e, em seguida, clique em **Gerenciador de servidores**.

2.  No Gerenciador de servidores, em **Resumo de recursos**, escolha **Adicionar recursos**.

3.  Expanda o **.NET Framework 4,5**.

4.  Selecione **ativação do WCF** , se ainda não estiver selecionado. Em seguida, selecione **ativação http**.

5.  Clique em **Avançar** e siga as instruções para concluir a instalação.

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

A **base de identidade do Windows** no Lync Server 2013 requer a instalação do Windows Identity Foundation para dar suporte a cenários de autenticação do servidor para o servidor. O Windows Server 2008 R2 e o Windows Server 2012 exigem procedimentos diferentes para instalar a base de identidades do Windows. Selecione o sistema operacional do seu servidor na lista a seguir:

  - Windows Server 2008 R2 para Windows Server 2008 R2, você verifica se ele já foi instalado em seu computador. Para fazer isso, vá para **Adicionar/remover programas**, **Exibir atualizações instaladas**e procurar em **Windows** para a entrada do **Windows Identity Foundation (KB974405)**. Para obter detalhes sobre como instalar o Windows Identity [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.

  - Windows Server 2012 para Windows Server 2012, você usa o **Gerenciador de servidores** para instalar o Windows Identity Foundation. No **Assistente Adicionar funções e recursos**do Gerenciador de servidores, selecione **recursos**. Selecione **Windows Identity Foundation 3,5** na lista. Clique em **Avançar**e, em seguida, clique em **instalar**.

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>Software adicional para todos os servidores front-end e servidores Standard Edition

Todos os servidores de front-end e servidores Standard Edition também devem executar o IIS (serviços de informações da Internet) com determinados módulos. Além disso, todos os servidores de front-end e servidores da edição padrão em que a conferência, chamadas de aplicativo, anúncio ou grupos de resposta são implementadas devem executar o tempo de execução do Windows Media Format.

<div>

## <a name="internet-information-services-iis"></a>IIS (Serviços de Informações da Internet)

Os servidores front-end e servidores Standard Edition devem executar o IIS (serviços de informações da Internet), com os seguintes módulos:

  - Conteúdo estático

  - Documento padrão

  - Erros HTTP

  - ASP.NET

  - Extensibilidade .NET

  - Extensões da API de servidor da Internet (ISAPI)

  - Filtros ISAPI

  - Log HTTP

  - Ferramentas de log

  - Rastreamento

  - Autenticação do Windows

  - Requisição de filtro

  - Compressão de conteúdo estático

  - Compactação de conteúdo dinâmico

  - Console de gerenciamento IIS

  - Ferramentas e scripts de gerenciamento IIS

  - Autenticação anônima (instalada por padrão quando o IIS é instalado)

  - Autenticação de mapeamento de certificado de cliente

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Experiência em tempo de execução do Windows Media Format e área de trabalho do Windows

**Experiência da área de trabalho do Windows** Todos os servidores front-end e servidores Standard Edition em que a conferência será implantada devem ter o tempo de execução do Windows Media Format instalado, o que, com exceção do Windows Server 2012, é instalado como parte da experiência da área de trabalho do Windows. O Windows Server 2012 requer o Microsoft Media Foundation. O tempo de execução do Windows Media Format é necessário para executar os arquivos de áudio do Windows Media (. WMA) que os aplicativos de estacionamento de chamada, anúncio e resposta são reproduzidos para anúncios e músicas.

Recomendamos que você instale a experiência da área de trabalho do Windows antes de instalar o Lync Server 2013. Se o Lync Server 2013 não encontrar esse software no servidor, ele solicitará que você o instale e, em seguida, deverá reiniciar o servidor para concluir a instalação.

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Software adicional para servidores front-end e servidores Standard Edition em execução no Windows Server 2012

Os servidores front-end exigem o .NET 3,5, que não é instalado por padrão no Windows Server 2012. Para instalá-lo, coloque a mídia de instalação do Windows Server 2012 na unidade D e digite o seguinte:

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Para obter detalhes sobre como instalar o .NET 3,5 em servidores que executam o Windows Server 2012, consulte "Microsoft .NET <https://go.microsoft.com/fwlink/p/?linkid=275032>Framework 3,5 considerações de implantação" em.

</div>

<div>

## <a name="additional-software-for-directors"></a>Software adicional para directors

Os diretores devem executar o IIS (serviços de informações da Internet), com os seguintes módulos:

  - Conteúdo estático

  - Documento padrão

  - Erros HTTP

  - ASP.NET

  - Extensibilidade .NET

  - Extensões da API de servidor da Internet (ISAPI)

  - Filtros ISAPI

  - Log HTTP

  - Ferramentas de log

  - Rastreamento

  - Autenticação do Windows

  - Requisição de filtro

  - Compressão de conteúdo estático

  - Console de gerenciamento IIS

  - Ferramentas e scripts de gerenciamento IIS

  - Autenticação anônima (instalada por padrão quando o IIS é instalado)

  - Autenticação de mapeamento de certificado de cliente

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>Software adicional para servidores de front-end de chat persistente

Os servidores de front-end de chat persistente devem executar o enfileiramento de mensagens (também conhecido como MSMQ), que é um componente do Windows Server.

Para obter informações sobre como habilitar o MSMQ, [clique aqui.](https://technet.microsoft.com/en-us/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>Software adicional para servidores Edge

Os servidores de borda exigem o seguinte software:

  - Cada servidor executando o Lync Server 2013 deve ter a versão correta do Windows PowerShell 3,0 instalada. Para obter detalhes, consulte [instalando o Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - O Lync Server requer o Microsoft .NET Framework 4,5. Para o Lync Server 2013 instalado no Windows Server 2008 R2, você deve instalar manualmente a edição de 64 bits do Microsoft .NET Framework 4,5 no servidor antes de instalar o Lync Server 2013. Para instalá-lo manualmente, baixe a estrutura do Microsoft .NET 4,5 a partir do centro de download da Microsoft em[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - A **base de identidade do Windows** no Lync Server 2013 requer a instalação do Windows Identity Foundation para dar suporte a cenários de autenticação do servidor para o servidor. O Windows Server 2008 R2 e o Windows Server 2012 exigem procedimentos diferentes para instalar a base de identidades do Windows. Selecione o sistema operacional do seu servidor na lista a seguir:
    
      - Windows Server 2008 R2 para Windows Server 2008 R2, você verifica se ele já foi instalado em seu computador. Para fazer isso, vá para **Adicionar/remover programas**, **Exibir atualizações instaladas**e procurar em **Windows** para a entrada do **Windows Identity Foundation (KB974405)**. Para obter detalhes sobre como instalar o Windows Identity [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Foundation, consulte.
    
      - Windows Server 2012 para Windows Server 2012, você usa o **Gerenciador de servidores** para instalar o Windows Identity Foundation. No **Assistente Adicionar funções e recursos**do Gerenciador de servidores, selecione **recursos**. Selecione **Windows Identity Foundation 3,5** na lista. Clique em **Avançar**e, em seguida, clique em **instalar**.

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>Não instalar provedores de soquete em camadas em servidores de mídia

Não instale qualquer software cliente do Microsoft Internet Security and Acceleration (ISA) Server ou qualquer outro software de provedores de serviços em camadas (LSP) Winsock em qualquer servidor front-end ou servidores autônomos de mediação. A instalação deste software pode causar um desempenho de tráfego de mídia ruim.

</div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos de software de ferramentas administrativas no Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

