---
title: 'Lync Server 2013: ferramenta de diagnóstico de chamadas do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79009ce890e37e7238e3fef18f719fb3da411889
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Ferramenta de diagnóstico de chamadas do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-11-04_

A ferramenta de diagnóstico de chamadas (PCD) do Lync é um aplicativo baseado no cliente que permite que você veja como o estado atual da sua rede pode afetar a qualidade de áudio em uma próxima chamada do Enterprise Voice.

O PCD é mais útil em situações em que o último salto de uma rede provavelmente será o mais fraco (por exemplo, com laptops em uma rede Wi-Fi pública ou usuários domésticos). O PCD cria um pequeno fluxo de pacotes que atravessa o trecho final da rede. Em seguida, a ferramenta analisa o fluxo de pacotes para estimar como a tremulação e a perda desse trecho podem afetar a qualidade da chamada e, em seguida, fornece um relatório. Você pode executar o PCD continuamente no cliente, mesmo quando as chamadas estão sendo feitas. O fluxo de pacote não tem um efeito significativo sobre a largura de banda.

**A versão mais recente do PCD, versão 1,1, inclui os seguintes aprimoramentos:**

  - Suporte para senhas mais longas, que agora podem ter até 127 caracteres

  - Diagnóstico adicional para problemas de entrada de autenticação

  - Melhor suporte para implantações híbridas do Lync

  - Atualizações para o seletor de credenciais

  - Melhorias de estabilidade

Agradecemos todos os comentários. Envie todas as perguntas ou problemas de suporte para o alias de comentários <pcdfb@microsoft.com>do [PCD](mailto:pcdfb@microsoft.com) em.

Este tópico inclui as seguintes seções:

  - Versões do Lync PCD

  - Requisitos do sistema do Lync PCD

  - Recursos do Lync PCD

  - Executando o Lync PCD

  - Desinstalando o Lync PCD

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Versões do Lync PCD

Este tópico descreve as seguintes versões da ferramenta, disponível para download gratuito:

  - Aplicativo da área de[https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914)trabalho Windows ()

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Requisitos do sistema do Lync PCD

<div>


> [!NOTE]  
> O PCD requer que a UCWA (Unified Communications Web API) seja instalada e configurada para dar suporte a clientes móveis na implantação do Lync Server. O UCWA é instalado com o Lync Server.



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Requisitos do aplicativo da área de trabalho Windows

  - Qualquer edição do sistema operacional Windows 7 ou Windows 8

  - Microsoft .NET Framework 4,5 disponível em[https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Recursos do Lync PCD

O Lync PCD inclui os seguintes recursos:

  - Executar no padrão por demanda (intermitências de 2 minutos)

  - Executar em modo Always on (até 24 horas no modo de exibição encaixado)

  - Exibição histórica de suas execuções de teste

  - Diagnosticar falhas de logon (Lync PCD somente para Windows 8)

![Captura de tela de progresso de recursos do Lync PCD](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Captura de tela de progresso de recursos do Lync PCD")

  - Exibição gráfica de métricas de rede – MOS de rede, perda de pacotes e Tremulação de interentrada em tela inteira e modo de exibição instantâneo.

**Exibição de tela inteira**

![Gráficos de resultados de teste da ferramenta de diagnóstico de chamadas](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Gráficos de resultados de teste da ferramenta de diagnóstico de chamadas")

**Exibição ajustada**

![Resultados do teste de utilização da ferramenta de diagnóstico de chamadas](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Resultados do teste de utilização da ferramenta de diagnóstico de chamadas")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>Executando o Lync PCD

<div>

## <a name="running-windows-desktop-app"></a>Executando o aplicativo da área de trabalho Windows

1.  Para iniciar o PCD em um sistema Windows 7, selecione **diagnóstico de chamadas** no menu **Iniciar** .
    
    Para iniciar o PCD em um sistema Windows 8, selecione o ícone na tela inicial ou pesquise "diagnósticos de chamada".
    
    ![Ícone da ferramenta de diagnóstico de chamada](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Ícone da ferramenta de diagnóstico de chamada")

2.  Quando a ferramenta for iniciada, selecione seu método preferido de fornecer credenciais e selecione o modo operacional de rede na caixa de diálogo **Opções da ferramenta de diagnóstico de chamadas** e, em seguida, selecione **OK**:

3.  Selecione o botão **Iniciar teste** para começar a executar o diagnóstico.
    
    Se você selecionou a opção **usar credenciais de rede** , o teste começará imediatamente.
    
    Se você selecionou a opção **deixe-me digitar minhas credenciais** , a caixa de diálogo **segurança do Windows** será aberta. Depois de inserir suas credenciais, o teste é iniciado.

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>Desinstalando o Lync PCD

Para remover o Lync PCD, siga o procedimento para seu sistema operacional:

  - Em um sistema Windows 7, abra o **painel de controle**, selecione **programas e recursos**e clique duas vezes em **diagnóstico de chamadas do Lync 2013**.

  - Em um sistema Windows 8, clique com o botão direito do mouse no bloco PCD e clique em **desinstalar** na barra de aplicativos na parte inferior da tela iniciar.

</div>

</div>

<span> </span>

</div>

</div>

</div>

