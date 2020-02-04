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
ms.openlocfilehash: 004d3b30dc2c2886eb7a2d8977f1da062277cc92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Ferramenta de diagnóstico de chamadas do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-11-04_

A ferramenta de diagnóstico de chamadas (PCD) do Lync é um aplicativo baseado em cliente que permite que você veja como o estado atual da sua rede pode afetar a qualidade de áudio em uma próxima chamada de voz empresarial.

O PCD é mais útil em situações em que o último nó de uma rede é provavelmente o mais fraco (por exemplo, com laptops em uma rede WiFi pública ou em usuários domésticos). O PCD cria um fluxo de pacotes pequeno que atravessa o trecho final da rede. Em seguida, a ferramenta analisa o fluxo do pacote para estimar como a tremulação e a perda nesse segmento podem afetar a qualidade da chamada e, em seguida, fornecer um relatório. Você pode executar o PCD continuamente no cliente, mesmo quando as chamadas estiverem sendo feitas. O fluxo do pacote não tem um efeito significativo na largura de banda.

**A versão mais recente do PCD, versão 1,1, inclui os seguintes aprimoramentos:**

  - Suporte para senhas mais longas, que agora podem ter até 127 caracteres

  - Diagnósticos adicionais para problemas de entrada de autenticação

  - Melhor suporte para implantações híbridas do Lync

  - Atualizações do seletor de credenciais

  - Melhorias de estabilidade

Agradecemos qualquer feedback. Envie todas as perguntas ou problemas de suporte ao alias de [comentários](mailto:pcdfb@microsoft.com) do <pcdfb@microsoft.com>PCD em.

Este tópico inclui as seguintes seções:

  - Versões do Lync PCD

  - Requisitos do sistema do Lync PCD

  - Recursos do Lync PCD

  - Executando o Lync PCD

  - Desinstalar o Lync PCD

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Versões do Lync PCD

Este tópico descreve as seguintes versões da ferramenta, disponível para download gratuito:

  - Aplicativo da área de[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)trabalho do Windows ()

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Requisitos do sistema do Lync PCD

<div>


> [!NOTE]  
> O PCD requer que a API da Web de comunicação unificada (UCWA) seja instalada e configurada para dar suporte a clientes móveis na implantação do Lync Server. O UCWA é instalado com o Lync Server.



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Requisitos do aplicativo da área de trabalho do Windows

  - Qualquer edição do sistema operacional Windows 7 ou Windows 8

  - Microsoft .NET Framework 4,5 disponível em[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Recursos do Lync PCD

O Lync PCD inclui os seguintes recursos:

  - Executar no padrão sob demanda (intermitências de 2 minutos)

  - Executar em modo (até 24 horas no modo de exibição ajustado)

  - Modo de exibição histórico de suas execuções de teste

  - Diagnosticar falhas de entrada (somente Lync PCD para Windows 8)

![Captura de tela de progresso do recurso de entrada do Lync PCD](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Captura de tela de progresso do recurso de entrada do Lync PCD")

  - Modo de exibição gráfico de métricas de rede – MOS de rede, perda de pacotes e Tremulação de interentrada em tela cheia e exibição ajustada.

**Modo de exibição de tela inteira**

![Gráficos de resultado de teste da ferramenta de diagnóstico de chamada](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Gráficos de resultado de teste da ferramenta de diagnóstico de chamada")

**Modo de exibição ajustado**

![Resultados do teste de utilização da ferramenta de diagnóstico de chamada](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Resultados do teste de utilização da ferramenta de diagnóstico de chamada")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>Executando o Lync PCD

<div>

## <a name="running-windows-desktop-app"></a>Executando o aplicativo da área de trabalho do Windows

1.  Para iniciar o PCD em um sistema Windows 7, selecione o recurso de **diagnóstico de chamadas** no menu **Iniciar** .
    
    Para iniciar o PCD em um sistema do Windows 8, selecione o ícone na tela inicial ou procure por "getcall Diagnostics".
    
    ![Ícone da ferramenta de diagnóstico de chamada](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Ícone da ferramenta de diagnóstico de chamada")

2.  Quando a ferramenta for iniciada, selecione seu método preferido de fornecimento de credenciais e selecione o modo operacional de rede na caixa de diálogo **Opções da ferramenta de diagnóstico de chamadas** e, em seguida, selecione **OK**:

3.  Selecione o botão **Iniciar teste** para começar a executar o diagnóstico.
    
    Se você tiver selecionado a opção **usar credenciais de rede** , o teste começará imediatamente.
    
    Se você tiver selecionado a opção **deixe-me digitar minhas credenciais** , a caixa de diálogo **segurança do Windows** será aberta. Depois de inserir suas credenciais, o teste é iniciado.

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>Desinstalar o Lync PCD

Para remover o Lync PCD, siga o procedimento para seu sistema operacional:

  - Em um sistema Windows 7, abra o **painel de controle**, selecione **programas e recursos**e clique duas vezes em **diagnóstico de chamada do Lync 2013**.

  - Em um sistema Windows 8, clique com o botão direito do mouse no bloco do PCD e clique em **desinstalar** na barra de aplicativos na parte inferior da tela iniciar.

</div>

</div>

<span> </span>

</div>

</div>

</div>

