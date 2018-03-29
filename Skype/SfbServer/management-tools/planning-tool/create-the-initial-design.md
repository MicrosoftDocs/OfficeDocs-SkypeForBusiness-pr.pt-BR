---
title: Criar o design de topologia inicial para o Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Depois de concluir a instalação do Skype para ferramenta de planejamento do Business Server, você estará pronto para iniciar a ferramenta de planejamento e começar a projetar o Skype proposto para infraestrutura de Business Server 2015.
ms.openlocfilehash: 9925ad9e4294ef2a1e4b90f6e1de9780bbb83260
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Criar o design de topologia inicial para o Skype for Business Server 2015
 
Depois de concluir a instalação do Skype para ferramenta de planejamento do Business Server, você estará pronto para iniciar a ferramenta de planejamento e começar a projetar o Skype proposto para infraestrutura de Business Server 2015.
  
> [!NOTE]
>  A ferramenta de planejamento é uma ferramenta conduzida por assistente com guias detalhados para informar seu processo de tomada de decisão em projetar sua topologia e sites. Este tópico destina-se e não como um guia exaustiva, mas simplesmente para ajudar você a começar usando a ferramenta de planejamento em sessões de design.
  
### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Para começar a usar a ferramenta de planejamento e criar o design inicial

1. Inicie o Skype para ferramenta de planejamento do Business Server 2015: clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server 2015**e, em seguida, clique em **Ferramenta de planejamento**.
    
2. Depois que a ferramenta de planejamento tiver iniciado, a página **Bem-vindo à ferramenta de planejamento do Skype para Business Server 2015** é exibida. Escolha uma das seguintes opções para começar seu design:
    
   - **Opção 1: Introdução** Clicando em **Introdução** fornece uma série específica de perguntas de entrevista com seleções relevantes para definir os critérios. Após ter finalizado a seção de entrevista  **Iniciando** inicial, você continua com  **Design de sites** para definir sua arquitetura de site. Para concluir esta opção, continue na etapa 3.
    
   - **Opção 2: projetar Sites** Clicar em **Design Sites** na página de boas-vindas ignora as perguntas da entrevista apresentadas na seção **Introdução** . Com esta opção, as informações que teriam sido recolhidas com as respostas às perguntas da entrevistas na seção **Introdução** são definidas como os valores padrão. Ao clicar em **Projetar sites**, o designer experiente pode ignorar a entrevista inicial e alterar os valores padrões conforme necessário na página inicial  **Sites centrais**. Para concluir esta opção, pule as etapas de 3 a 5 e comece na etapa 6.
    
   - **Opção 3: exibir sua topologia salva** Se você já tiver concluído e salva uma topologia por meio do uso de anterior da ferramenta de planejamento, pode ignorar a maioria das seguintes etapas e iniciar abrindo e exibir a topologia. Você também pode fazer alterações e atualizações na topologia, salvá-la novamente e exportá-la para o Microsoft Excel ou Microsoft Visio. Para concluir esta opção, pule as etapas de 3 a 12 e comece na etapa 13.
    
3. Clique em **Começar** para começar a projetar sua Skype para a topologia de negócios Server 2015.
    
4. Responda cada seção selecionando os critérios apropriados para seu design e clique em **Avançar ** para prosseguir à próxima página do assistente. Clique em **Voltar** para fazer alterações nas páginas anteriores.
    
    > [!TIP]
    > Cada página possui uma descrição do critério de seleção e recomendações com base nas práticas preferidas e no planejamento de capacidade. Se você precisar detalhes adicionais, clique em **Saiba mais** para ler informações detalhadas do Skype para documentação de planejamento do Business Server 2015 no site Microsoft TechNet. Você deve ter uma conectividade com a Internet para acessar o site da Microsoft TechNet.
  
5. Selecione as opções adequadas para seu design. Após o critério inicial ser definido, uma página confirmará que sua Visão Geral dos Recursos está concluída. 
    
6. Clique em **Sites de Design** para definir seu local central.
    
    > [!NOTE]
    > Cada Skype para Business Server 2015 topologia terá pelo menos um site central. Seu design pode ter um único site central, um site central com um número de sites de filiais, um número de sites centrais ou um número de sites central com sites de filiais associados a cada site central. 
  
7. Em **Nome do Site**, digite o nome que identificará este site central.
    
8. Em **Usuários hospedados do Site**, digite o número esperado de usuários simultâneos de local que serão hospedados neste site central.
    
9. Em **Usuários hospedados em nuvem**, digite o número esperado de usuários simultâneos online que serão hospedados neste site central.
    
10. Modifique as seleções para Colaboração Online, Usuários, Voz, Opções de Implantação Adicional ou Aplicativos do Servidor conforme necessário.
    
    > [!IMPORTANT]
    > Neste ponto do design, você pode apenas selecionar ou desmarcar opções de sua implantação. No entanto, você pode configurar mais opções em uma fase posterior da ferramenta de planejamento. Existem também opções que não estão disponíveis e não podem ser desmarcadas. Além disso, talvez você precisa desmarcar uma opção para desmarcar outra. Por exemplo, se você desmarcar a opção **Enterprise Voice** em Voz, as opções **Grupo de Resposta**, **Anúncio** e **Estacionamento de Chamada** em Aplicativos do Servidor (todas elas recursos do Enterprise Voice) também serão desmarcadas.
  
11. Após definir um nome de site e número de usuários, clique em  **Avançar**.
    
12. As páginas a seguir solicita informações sobre SIP domínios, configurações de conferência, as configurações de voz e infra-estrutura, UM do Exchange, acesso de usuário externo, Chat persistente configurações, as configurações do cliente, opções de colocação e sites de filiais. Responda a essas perguntas conforme apropriado.
    
13. A pergunta final pergunta se você deseja criar outro site central. Se você selecionar **Sim**, a ferramenta de planejamento retorna para a página Sites centrais. Se selecionar **Não **, clique em **Avançar ** e, depois, em **Desenho ** para obter uma exibição de alto nível da topologia global.
    
14. Para exibir uma topologia existente, clique em  **Exibir**.
    
15. Clique no arquivo .xml que representa a topologia salva anteriormente e clique em **Abrir**.
    
16. A ferramenta de planejamento exibe a página de topologia Global. Agora você pode começar a edição, atualizando ou alterar a topologia usando as ferramentas disponíveis na ferramenta de planejamento.
    
## <a name="see-also"></a>Consulte também

#### 

[Editando o Design](http://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)

