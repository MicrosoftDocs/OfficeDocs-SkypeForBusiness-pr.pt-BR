---
title: 'Lync Server 2013: criar o design de topologia inicial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed95696dc0acad9030615f8a031672f8abf3a136
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>Criar o design de topologia inicial para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Após concluir a instalação da ferramenta de planejamento do Lync Server 2013, você está pronto para iniciar a ferramenta de planejamento e começar a criar a infraestrutura proposta do Lync Server 2013.

<div>


> [!NOTE]  
> A ferramenta de planejamento é uma ferramenta orientada por assistente com guias detalhadas para informar o processo de tomada de decisão na criação de sites e topologia. Este tópico não se destina a um guia abrangente, mas simplesmente para ajudá-lo a começar a usar a ferramenta de planejamento nas sessões de design.



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Para iniciar usando a Ferramenta de Planejamento e criar o design inicial

1.  Inicie a ferramenta de planejamento do Lync Server 2013: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **ferramenta de planejamento**.

2.  Após o início da ferramenta de planejamento, a página **Bem-vindo à ferramenta de planejamento para o Microsoft Lync Server 2013** é exibida. Escolha uma das seguintes opções para começar seu design:
    
      - **Opção 1:**   introdução **ao clique em introdução fornece** uma série específica de perguntas de entrevista com seleções relevantes para definir os critérios. Após ter finalizado a seção de entrevista **Iniciando** inicial, você continua com **Design de sites** para definir sua arquitetura de site. Para concluir esta opção, continue na etapa 3.
    
      - **Opção 2: design sites**   clicando em **sites de design** na página de boas-vindas ignora as perguntas de entrevista apresentadas na seção **introdução** . As informações que seriam coletadas respondendo às perguntas de entrevista na seção **introdução** é definida como valores padrão com essa opção. Ao clicar em **sites de design**, o designer experiente pode ignorar a entrevista inicial e alterar os valores padrão, conforme necessário, na página inicial dos **sites centrais** . Para concluir esta opção, pule as etapas 3 a 5 e inicie na etapa 6.
    
      - **Opção 3: exibir sua topologia**   salva se você já tiver concluído e salvo uma topologia por meio do uso anterior da ferramenta de planejamento, poderá ignorar a maioria dessas etapas e começar abrindo e exibindo a topologia. Você também pode fazer alterações e atualizações na topologia, salvá-la novamente e, em seguida, exportá-la para o Microsoft Excel ou Microsoft Visio. Para concluir esta opção, pule as etapas 3 a 12 e inicie na etapa 13.

3.  Clique **em introdução para** começar a criar sua topologia do Lync Server 2013.

4.  Responda cada seção selecionando o critério adequado para seu design e clique em **Avançar** para continuar com a próxima página do Assistente. Clique em **voltar** para fazer alterações nas páginas anteriores.
    
    <div>
    

    > [!TIP]  
    > Cada página possui uma descrição do critério de seleção e recomendações com base nas práticas preferidas e no planejamento de capacidade. Se você precisar de mais detalhes, clique em <STRONG>saiba mais</STRONG> para ler informações detalhadas da documentação de planejamento do Lync Server 2013 no site da Microsoft TechNet. Você deve ter uma conectividade com a Internet para acessar o site da Microsoft TechNet.

    
    </div>

5.  Selecione as opções adequadas para seu design. Após o critério inicial ser definido, uma página confirmará que sua Visão Geral dos Recursos está concluída.

6.  Clique em **design de sites** para definir seu site central.
    
    <div>
    

    > [!NOTE]  
    > Cada topologia do Lync Server 2013 terá pelo menos um site central. O design pode ter um único site central, um site central com vários sites de filiais, vários sites centrais ou vários sites centrais com sites de filial associados a cada site central.

    
    </div>

7.  Em **nome do site**, digite o nome que identificará esse site central.

8.  Em **usuários hospedados no site**, digite o número esperado de usuários simultâneos locais que serão hospedados neste site central.

9.  Em **usuários hospedados na nuvem**, digite o número esperado de usuários simultâneos online que serão hospedados neste site central.

10. Modifique as seleções para colaboração online, usuários, voz, opções de implantação adicionais ou aplicativos de servidor, conforme necessário.
    
    <div>
    

    > [!IMPORTANT]  
    > Neste ponto no design, você só pode selecionar ou desmarcar opções para sua implantação. No entanto, você pode configurar mais opções em uma fase posterior da ferramenta de planejamento. Existem também outras opções que não estão disponíveis e não podem ser desmarcadas. Além disso, você pode precisar desmarcar uma opção para desmarcar outra. Por exemplo, se você desmarcar a opção <STRONG>Enterprise Voice</STRONG> em voz, as opções <STRONG>grupo de resposta</STRONG>, <STRONG>anúncio</STRONG>e <STRONG>estacionamento de chamada</STRONG> em aplicativos de servidor (todos os recursos do Enterprise Voice) também serão desmarcadas.

    
    </div>

11. Após definir um nome de site e número de usuários, clique em **Avançar**.

12. As páginas a seguir solicitam informações sobre domínios SIP, configurações de conferência, configurações de voz e infraestrutura, a UM do Exchange, acesso de usuário externo, configurações de chat persistente, configurações de cliente, opções de colocação e sites de filial. Respondas estas perguntas conforme adequado.

13. A pergunta final pergunta se você deseja criar outro site central. Se você selecionar **Sim**, a ferramenta de planejamento voltará para a página sites centrais. Se você selecionar **não**, clique em **Avançar**e, em seguida, clique em **desenhar** para exibir o modo de exibição de topologia global de alto nível.

14. Para exibir uma topologia existente, clique em **Exibir**.

15. Clique no arquivo .xml que representa a topologia salva anteriormente e clique em **Abrir**.

16. A ferramenta de planejamento exibe a página de topologia global. Agora você pode começar a editar, atualizar ou alterar a topologia usando as ferramentas disponíveis na ferramenta de planejamento.

</div>

<div>

## <a name="see-also"></a>Confira Também


[Editando o design no Lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

