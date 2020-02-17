---
title: 'Lync Server 2013: executando preparação da floresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9cb09b04ca42c032f042ed7970452f70982e016
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a>Executando a preparação da floresta para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-29_

Você pode usar os cmdlets de instalação ou do Shell de gerenciamento do Lync Server para preparar a floresta. O cmdlet que prepara a floresta é **Enable-CsAdForest**.

Depois de preparar a floresta, você deverá verificar se as configurações globais foram replicadas antes de executar a preparação do domínio.

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>Para usar a Instalação para preparar a floresta

1.  Faça logon em um computador que seja parte de um domínio como membro do grupo Administradores de Empresa para o domínio raiz da floresta.

2.  Na pasta ou mídia de instalação do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação.

3.  Clique em **Preparar o Active Directory** e espere que o estado da implantação seja determinado.

4.  Na **Etapa 3: Preparar Floresta Atual**, clique em **Executar**.

5.  Na página **Preparar Floresta**, clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > A preparação da floresta permite que você escolha onde colocar os grupos universais para o Lync Server 2013. Escolha o local consistente com as exigências de sua organização.

    
    </div>

6.  Na página **Executando Comandos**, procure por **Status da tarefa: concluída** e clique em **Exibir Log**.

7.  Na coluna **ação** , expanda **Forest prep**, procure um ** \<\> ** resultado de execução de êxito no final de cada tarefa para verificar se a preparação da floresta foi concluída com êxito, feche o log e clique em **concluir**.

8.  Aguarde a replicação do Active Directory ser concluída ou force a replicação em todos os controladores de domínio listados no snap-in **Sites e Serviços do Active Directory** no controlador de domínio raiz da floresta, antes de executar a preparação do domínio. Force a replicação entre os controladores de domínio em todos os sites do Active Directory para que a replicação nos sites ocorra dentro de alguns minutos.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>Para usar os cmdlets para preparar a floresta

1.  Faça logon em um computador que ingressou em um domínio como membro do grupo Admins. do Domínio no domínio raiz da floresta.

2.  Instale os componentes principais do Lync Server da seguinte maneira:
    
    1.  Na pasta ou mídia de instalação do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.
    
    2.  Se for solicitado que você instale o Microsoft Visual C++ Redistributable, clique em **Sim**.
    
    3.  A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server. Escolha o local padrão ou **Procure** um local de sua escolha e clique em **Instalar**.
    
    4.  Na página Contrato de Licença, marque **Aceito os termos do contrato de licença** e clique em **OK**. O instalador instala os componentes principais do Lync Server 2013.

3.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

4.  Sejam
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    Por exemplo:
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    Se você não especificar o parâmetro GroupDomain, o valor padrão será o domínio local. Se grupos universais tiverem sido criados anteriormente em um domínio que não seja o domínio padrão, será necessário especificar explicitamente o parâmetro GroupDomain.

5.  Aguarde a replicação do Active Directory ser concluída ou force a replicação em todos os controladores de domínio listados no snap-in **Sites e Serviços do Active Directory** no controlador de domínio raiz da floresta, antes de executar a preparação do domínio.

6.  Verificar se a preparação da floresta teve êxito. Execute:
    
        Get-CsAdForest 
    
    Este cmdlet retorna um valor de **FORESTSETTINGS\_\_do estado\_da LC pronto** se a preparação da floresta tiver sido bem-sucedida.

</div>

<div>

## <a name="see-also"></a>Confira Também


[Usando cmdlets para reverter a preparação da floresta para o Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[Preparando a floresta para o Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

