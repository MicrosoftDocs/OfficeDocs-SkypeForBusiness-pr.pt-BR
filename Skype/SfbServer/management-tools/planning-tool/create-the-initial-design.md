---
title: Criar o design de topologia inicial para o Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Depois de concluir a instalação da ferramenta de planejamento do Skype for Business Server, você estará pronto para iniciar a ferramenta de planejamento e começar a projetar a infraestrutura proposta do Skype for Business Server 2015.
ms.openlocfilehash: 47a3725c1307bd6efe57fa07a955004bd6e5ff29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274265"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Create the initial topology design for Skype for Business Server 2015

Depois de concluir a instalação da ferramenta de planejamento do Skype for Business Server, você estará pronto para iniciar a ferramenta de planejamento e começar a projetar a infraestrutura proposta do Skype for Business Server 2015.

> [!NOTE]
>  A ferramenta de planejamento é uma ferramenta orientada por assistente com guias detalhadas para informar o processo de tomada de decisões na criação de sites e topologias. Este tópico não se destina como um guia exaustivo, mas basta ajudá-lo a começar a usar a ferramenta de planejamento em suas sessões de design.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Para começar a usar a ferramenta de planejamento e criar o design inicial

1. Inicie a ferramenta de planejamento do Skype for Business Server 2015: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business Server 2015**e, em seguida, clique em **ferramenta de planejamento**.

2. Após o início da ferramenta de planejamento, a página **Bem-vindo à ferramenta de planejamento para o Skype for Business Server 2015** é exibida. Escolha uma das seguintes opções para começar seu design:

   - **Opção 1:** introdução Clicar **** em introdução fornece uma série específica de perguntas de entrevista com seleções relevantes para definir os critérios. Após ter finalizado a seção de entrevista  **Iniciando** inicial, você continua com  **Design de sites** para definir sua arquitetura de site. Para concluir esta opção, continue na etapa 3.

   - **Opção 2: sites de design** Clicar em **sites de design** na página de boas-vindas ignora as perguntas **** da entrevista apresentadas na seção Introdução. Com esta opção, as informações que teriam sido recolhidas com as respostas às perguntas da entrevistas na seção **Introdução** são definidas como os valores padrão. Ao clicar em **Projetar sites**, o designer experiente pode ignorar a entrevista inicial e alterar os valores padrões conforme necessário na página inicial  **Sites centrais**. Para concluir esta opção, pule as etapas de 3 a 5 e comece na etapa 6.

   - **Opção 3: exibir sua topologia salva** Se já tiver concluído e salvo uma topologia por meio do uso anterior da ferramenta de planejamento, você poderá ignorar a maioria dessas etapas e começar abrindo e exibindo a topologia. Você também pode fazer alterações e atualizações na topologia, salvá-la novamente e exportá-la para o Microsoft Excel ou Microsoft Visio. Para concluir esta opção, pule as etapas de 3 a 12 e comece na etapa 13.

3. Clique **** em introdução para começar a criar sua topologia do Skype for Business Server 2015.

4. Responda cada seção selecionando os critérios apropriados para seu design e clique em **Avançar ** para prosseguir à próxima página do assistente. Clique em **Voltar** para fazer alterações nas páginas anteriores.

    > [!TIP]
    > Cada página possui uma descrição do critério de seleção e recomendações com base nas práticas preferidas e no planejamento de capacidade. Se você precisar de mais detalhes, clique em **saiba mais** para ler informações detalhadas da documentação de planejamento do Skype for Business Server 2015 no website da Microsoft. Você deve ter conectividade com a Internet para acessar o website da Microsoft.

5. Selecione as opções adequadas para seu design. Após o critério inicial ser definido, uma página confirmará que sua Visão Geral dos Recursos está concluída.

6. Clique em **design sites** para definir seu site central.

    > [!NOTE]
    > Cada topologia do Skype for Business Server 2015 terá pelo menos um site central. Seu design pode ter um único site central, um site central com vários sites de filiais, vários sites centrais ou vários sites centrais com sites de filiais associados a cada site central.

7. Em **nome do site**, digite o nome que identificará esse site central.

8. Em **usuários**de residências do site, digite o número esperado de usuários simultâneos locais que serão hospedados neste site central.

9. Em **usuários de casa na nuvem**, digite o número esperado de usuários simultâneos online que serão hospedados neste site central.

10. Modifique as seleções para Colaboração Online, Usuários, Voz, Opções de Implantação Adicional ou Aplicativos do Servidor conforme necessário.

    > [!IMPORTANT]
    > Neste ponto do design, você pode apenas selecionar ou desmarcar opções de sua implantação. No entanto, você pode configurar mais opções em uma fase posterior da ferramenta de planejamento. Existem também opções que não estão disponíveis e não podem ser desmarcadas. Além disso, talvez você precisa desmarcar uma opção para desmarcar outra. Por exemplo, se você desmarcar a opção **Enterprise Voice** em Voz, as opções **Grupo de Resposta**, **Anúncio** e **Estacionamento de Chamada** em Aplicativos do Servidor (todas elas recursos do Enterprise Voice) também serão desmarcadas.

11. Após definir um nome de site e número de usuários, clique em  **Avançar**.

12. As páginas a seguir pedem informações sobre domínios SIP, configurações de conferência, configurações de voz e infraestrutura, Exchange UM, acesso de usuário externo, configurações de chat persistente, configurações de cliente, opções de colocação e sites de ramificação. Responda a essas perguntas conforme apropriado.

13. A pergunta final pergunta se você deseja criar outro site central. Se você selecionar **Sim**, a ferramenta de planejamento retornará para a página sites centrais. Se selecionar **Não **, clique em **Avançar ** e, depois, em **Desenho ** para obter uma exibição de alto nível da topologia global.

14. Para exibir uma topologia existente, clique em  **Exibir**.

15. Clique no arquivo .xml que representa a topologia salva anteriormente e clique em **Abrir**.

16. A ferramenta de planejamento exibe a página global Topology. Agora você pode começar a editar, atualizar ou alterar a topologia usando as ferramentas disponíveis na ferramenta de planejamento.

## <a name="see-also"></a>Confira também

[Editing the Design](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
