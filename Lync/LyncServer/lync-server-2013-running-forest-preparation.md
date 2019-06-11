---
title: 'Lync Server 2013: Executando preparação de floresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b011623b9091c1c707ae77381dacb99ba4642a21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a>Executando preparação de floresta para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-29_

Você pode usar os cmdlets do Shell de gerenciamento do Lync Server e do setup para preparar a floresta. O cmdlet que prepara a floresta é **Enable-CsAdForest**.

Depois de preparar a floresta, você deve verificar se as configurações globais foram duplicadas antes de executar a preparação do domínio.

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>Para usar a instalação para preparar a floresta

1.  Faça logon em um computador que esteja associado a um domínio como membro do grupo Administradores de empresa do domínio raiz da floresta.

2.  Na pasta de instalação ou mídia do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação.

3.  Clique em **Preparar o Active Directory** e espere que o estado da implantação seja determinado.

4.  Na **etapa 3: preparar a floresta atual**, clique em **executar**.

5.  Na página **preparar floresta** , clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > A preparação da floresta permite que você escolha onde colocar os grupos universais do Lync Server 2013. Escolha um local que atenda aos requisitos de sua organização.

    
    </div>

6.  Na página **Executando Comandos**, procure por **Status da tarefa: Concluída** e clique em **Exibir Log**.

7.  Na coluna **Action (ação** ), expanda **Forest prep**, procure um ** \<\> ** resultado de execução de sucesso no final de cada tarefa para verificar se a preparação da floresta foi concluída com êxito, feche o log e clique em **concluir**.

8.  Aguarde a conclusão da replicação do Active Directory ou force a replicação para todos os controladores de domínio listados no snap-in **sites e serviços do Active Directory** para o controlador de domínio raiz da floresta, antes de executar a preparação do domínio. Force a replicação entre os controladores de domínio em todos os sites do Active Directory para fazer com que a replicação dentro dos sites ocorra em minutos.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>Para usar cmdlets para preparar a floresta

1.  Faça logon em um computador que esteja associado a um domínio como membro do grupo Domain admins no domínio raiz da floresta.

2.  Instale os componentes principais do Lync Server da seguinte maneira:
    
    1.  Na pasta de instalação ou mídia do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.
    
    2.  Se você for solicitado a instalar o Microsoft Visual C++ Redistributable, clique em **Sim**.
    
    3.  A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server. Escolha o local padrão ou **navegue** até um local de sua escolha e clique em **instalar**.
    
    4.  Na página contrato de licença, marque **a opção aceito os termos do contrato de licença**e clique em **OK**. O instalador instala os componentes principais do Lync Server 2013.

3.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

4.  Execute:
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    Por exemplo:
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    Se você não especificar o parâmetro GroupDomain, o valor padrão será o domínio local. Se grupos universais foram criados anteriormente em um domínio que não seja o domínio padrão, você deve especificar o parâmetro GroupDomain explicitamente.

5.  Aguarde a conclusão da replicação do Active Directory ou force a replicação para todos os controladores de domínio listados no snap-in **sites e serviços do Active Directory** para o controlador de domínio raiz da floresta, antes de executar a preparação do domínio.

6.  Verifique se a preparação da floresta foi bem-sucedida. Execute:
    
        Get-CsAdForest 
    
    Esse cmdlet retorna um valor do **estado\_\_\_FORESTSETTINGS da LC pronto** se a preparação da floresta tiver sido bem-sucedida.

</div>

<div>

## <a name="see-also"></a>Confira também


[Usando cmdlets para reverter preparação da floresta no Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[Preparando a floresta para Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

