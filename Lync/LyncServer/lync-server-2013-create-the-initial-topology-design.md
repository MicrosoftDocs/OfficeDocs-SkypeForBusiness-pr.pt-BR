---
title: 'Lync Server 2013: criar o design inicial da topologia'
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
ms.openlocfilehash: 7fc8d3e731c2772b275dd861c41b8c10f2127a2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>Criar o design de topologia inicial para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Após concluir a instalação do Lync Server 2013, ferramenta de planejamento, você estará pronto para iniciar a ferramenta de planejamento e começar a projetar a infraestrutura proposta do Lync Server 2013.

<div>


> [!NOTE]  
> A ferramenta de planejamento é uma ferramenta orientada por assistente com guias detalhadas para informar o processo de tomada de decisões na criação de sites e topologias. Este tópico não se destina como um guia exaustivo, mas basta ajudá-lo a começar a usar a ferramenta de planejamento em suas sessões de design.



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Para começar a usar a ferramenta de planejamento e criar o design inicial

1.  Inicie o Lync Server 2013, ferramenta de planejamento: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **ferramenta de planejamento**.

2.  Após o início da ferramenta de planejamento, a página **Bem-vindo à ferramenta de planejamento para o Microsoft Lync Server 2013** é exibida. Escolha uma das seguintes opções para começar seu design:
    
      - **Opção 1:**   comece **a clicar em introdução fornece** uma série específica de perguntas de entrevista com seleções relevantes para definir os critérios. Após ter finalizado a seção de entrevista  **Iniciando** inicial, você continua com  **Design de sites** para definir sua arquitetura de site. Para concluir esta opção, continue na etapa 3.
    
      - **Opção 2: sites**   de design clicar em **sites de design** na página de boas-vindas ignora as perguntas da entrevista apresentadas **na seção Introdução** . Com esta opção, as informações que teriam sido recolhidas com as respostas às perguntas da entrevistas na seção **Introdução** são definidas como os valores padrão. Ao clicar em **Projetar sites**, o designer experiente pode ignorar a entrevista inicial e alterar os valores padrões conforme necessário na página inicial  **Sites centrais**. Para concluir esta opção, pule as etapas de 3 a 5 e comece na etapa 6.
    
      - **Opção 3: exibir sua topologia**   salva se você já tiver concluído e salvo uma topologia por meio do uso anterior da ferramenta de planejamento, poderá ignorar a maioria dessas etapas e começar abrindo e exibindo a topologia. Você também pode fazer alterações e atualizações na topologia, salvá-la novamente e exportá-la para o Microsoft Excel ou Microsoft Visio. Para concluir esta opção, pule as etapas de 3 a 12 e comece na etapa 13.

3.  Clique **em introdução para** começar a criar sua topologia do Lync Server 2013.

4.  Responda cada seção selecionando os critérios apropriados para seu design e clique em **Avançar ** para prosseguir à próxima página do assistente. Clique em **Voltar** para fazer alterações nas páginas anteriores.
    
    <div>
    

    > [!TIP]  
    > Cada página possui uma descrição do critério de seleção e recomendações com base nas práticas preferidas e no planejamento de capacidade. Se você precisar de mais detalhes, clique em <STRONG>saiba mais</STRONG> para ler informações detalhadas na documentação de planejamento do Lync Server 2013 no site do Microsoft TechNet. Você deve ter uma conectividade com a Internet para acessar o site da Microsoft TechNet.

    
    </div>

5.  Selecione as opções adequadas para seu design. Após o critério inicial ser definido, uma página confirmará que sua Visão Geral dos Recursos está concluída.

6.  Clique em **design sites** para definir seu site central.
    
    <div>
    

    > [!NOTE]  
    > Cada topologia do Lync Server 2013 terá pelo menos um site central. Seu design pode ter um único site central, um site central com vários sites de filiais, vários sites centrais ou vários sites centrais com sites de filiais associados a cada site central.

    
    </div>

7.  Em **nome do site**, digite o nome que identificará esse site central.

8.  Em **usuários de residências do site**, digite o número esperado de usuários simultâneos locais que serão hospedados neste site central.

9.  Em **usuários de casa na nuvem**, digite o número esperado de usuários simultâneos online que serão hospedados neste site central.

10. Modifique as seleções para Colaboração Online, Usuários, Voz, Opções de Implantação Adicional ou Aplicativos do Servidor conforme necessário.
    
    <div>
    

    > [!IMPORTANT]  
    > Neste ponto do design, você pode apenas selecionar ou desmarcar opções de sua implantação. No entanto, você pode configurar mais opções em uma fase posterior da ferramenta de planejamento. Existem também opções que não estão disponíveis e não podem ser desmarcadas. Além disso, talvez você precisa desmarcar uma opção para desmarcar outra. Por exemplo, se você desmarcar a opção <STRONG>Enterprise Voice</STRONG> em Voz, as opções <STRONG>Grupo de Resposta</STRONG>, <STRONG>Anúncio</STRONG> e <STRONG>Estacionamento de Chamada</STRONG> em Aplicativos do Servidor (todas elas recursos do Enterprise Voice) também serão desmarcadas.

    
    </div>

11. Após definir um nome de site e número de usuários, clique em  **Avançar**.

12. As páginas a seguir pedem informações sobre domínios SIP, configurações de conferência, configurações de voz e infraestrutura, Exchange UM, acesso de usuário externo, configurações de chat persistente, configurações de cliente, opções de colocação e sites de ramificação. Responda a essas perguntas conforme apropriado.

13. A pergunta final pergunta se você deseja criar outro site central. Se você selecionar **Sim**, a ferramenta de planejamento retornará para a página sites centrais. Se selecionar **Não **, clique em **Avançar ** e, depois, em **Desenho ** para obter uma exibição de alto nível da topologia global.

14. Para exibir uma topologia existente, clique em  **Exibir**.

15. Clique no arquivo .xml que representa a topologia salva anteriormente e clique em **Abrir**.

16. A ferramenta de planejamento exibe a página global Topology. Agora você pode começar a editar, atualizar ou alterar a topologia usando as ferramentas disponíveis na ferramenta de planejamento.

</div>

<div>

## <a name="see-also"></a>Confira também


[Editando o design no Lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

