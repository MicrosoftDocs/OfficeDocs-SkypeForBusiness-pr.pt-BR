---
title: Mesclar usando o assistente de mesclagem do construtor de topologia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8a65dab8cb99b35821f12c5871ae52f608ae344
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>Mesclar usando o assistente de mesclagem do construtor de topologia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

1.  Baixe a implantação existente usando o construtor de topologias.

2.  No menu **ação** , selecione mesclar o **Office communications Server 2007 R2**.

3.  Click **Next**.

4.  Em **especificar a configuração de borda**, clique em **Adicionar**.
    
    ![Assistente de topologia de mesclagem, especificar a página de configuração de borda] (images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Assistente de topologia de mesclagem, especificar a página de configuração de borda")  

5.  Em **especificar tipo de borda**, insira o tipo de configuração do servidor de borda e clique em **Avançar**. Este exemplo usa a opção **servidor de borda única** .
    
    <div>
    

    > [!IMPORTANT]  
    > A <STRONG>implantação de borda expandida</STRONG> não é uma configuração com suporte. Um <STRONG>servidor de borda expandida</STRONG> deve primeiro ser convertido em um <STRONG>servidor de borda único</STRONG> ou em um servidor de <STRONG>borda consolidada com balanceamento de carga</STRONG> .

    
    </div>

6.  Em **especificar as configurações de borda interna** , insira as informações relevantes para o FQDN e as portas internas do seu pool de bordas, conforme necessário, e clique em **Avançar**.
    
    ![Especificar a caixa de diálogo Configurações de borda interna] (images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Especificar a caixa de diálogo Configurações de borda interna")  

7.  Em **especificar borda externa**, insira as informações de FQDN do servidor de Webconferência para o servidor de borda.
    
    <div>
    

    > [!IMPORTANT]  
    > Antes de clicar em <STRONG>Avançar</STRONG>, siga o próximo passo deste procedimento. É muito importante que você não perca esta etapa.

    
    </div>

8.  Marque a caixa de seleção **este pool de bordas é usado para a Federação e conectividade de mensagem de chat pública** se você planeja usar o servidor de borda herdado do Office Communications Server 2007 R2 para Federação. Se você tiver vários servidores de Borda implantados, apenas um deles será habilitado para Federação. Se você não marcar esta caixa e decidir mais tarde que deseja habilitar a Federação, execute o assistente de mesclagem do construtor de topologias e publique sua topologia novamente.
    
    ![Caixa de diálogo servidor de borda, especificar a página de borda externa] (images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Caixa de diálogo servidor de borda, especificar a página de borda externa")  

9.  Em **especificar próximo salto**, digite o nome de domínio totalmente qualificado (FQDN) do próximo local do salto em seu ambiente. Clique em **Concluir**.
    
    ![Caixa de diálogo servidor de borda, especifique a página de próximo salto] (images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Caixa de diálogo servidor de borda, especifique a página de próximo salto")  

10. Em **especificar a configuração de borda**, se todos os seus servidores do Office Communications Server 2007 R2 Edge tiverem sido adicionados, clique em **Avançar**. Se você tiver mais servidores do Office Communications Server 2007 R2 Edge para adicionar, repita esse procedimento começando na etapa 4.

11. Em **especificar porta SIP interna** , selecione a configuração padrão (ou seja, se você não tiver modificado a porta SIP padrão). Altere conforme apropriado se você não estiver usando uma porta padrão do 5061 e clique em **Avançar**.

12. Em **Resumo**, clique em **Avançar** para começar a mesclar as topologias.

13. A página do assistente verifica se a mesclagem das topologias foi bem-sucedida.

14. Na coluna **status** , verifique se o valor é **êxito**e clique em **concluir**.

15. No painel esquerdo do construtor de topologias, agora você deve ver o **BackCompatSite**, que indica que o ambiente do Office Communications Server 2007 R2 foi mesclado com o Lync Server 2013.
    
    ![Construtor de topologias mostrando uma topologia mesclada] (images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Construtor de topologias mostrando uma topologia mesclada")  

16. No menu **ação** , clique em **publicar topologia**e, em seguida, clique em **Avançar**.

17. Quando o **Assistente de publicação** for concluído, clique em **concluir**.
    
    <div>
    

    > [!NOTE]  
    > É importante que você conclua o próximo tópico, <A href="import-policies-and-settings.md">importar políticas e configurações</A>, para garantir que as configurações de política herdadas sejam importadas para o Lync Server 2013.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

