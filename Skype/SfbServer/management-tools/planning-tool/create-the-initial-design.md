---
title: Criar o design de topologia inicial para o Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Depois de terminar de instalar a Ferramenta de Planejamento do Skype for Business Server, você estará pronto para iniciar a Ferramenta de Planejamento e começar a projetar a infraestrutura proposta do Skype for Business Server 2015.
ms.openlocfilehash: 7de930de8d7e194f14145c1a976fbe6b96cf234a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834961"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Criar o design de topologia inicial para o Skype for Business Server 2015

Depois de terminar de instalar a Ferramenta de Planejamento do Skype for Business Server, você estará pronto para iniciar a Ferramenta de Planejamento e começar a projetar a infraestrutura proposta do Skype for Business Server 2015.

> [!NOTE]
>  A Ferramenta de Planejamento é uma ferramenta orientada por assistente com guias detalhados para informar seu processo de tomada de decisão ao projetar seus sites e topologia. Este tópico não se destina como um guia completo, mas simplesmente para ajudá-lo a começar a usar a Ferramenta de Planejamento em suas sessões de design.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Para iniciar usando a Ferramenta de Planejamento e criar o design inicial

1. Inicie a Ferramenta de Planejamento do Skype for Business Server 2015: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business Server 2015** e em Ferramenta de **Planejamento.**

2. Depois que a Ferramenta de Planejamento tiver sido iniciada, a página Bem-vindo à Ferramenta de Planejamento do **Skype for Business Server 2015** será exibida. Escolha uma das seguintes opções para começar seu design:

   - **Opção 1: Começar** Clicar em **Começar fornece uma** série específica de perguntas de entrevista com seleções relevantes para definir os critérios. Após ter finalizado a seção de entrevista **Iniciando** inicial, você continua com **Design de sites** para definir sua arquitetura de site. Para concluir esta opção, continue na etapa 3.

   - **Opção 2: Projetar Sites** Clicar em **Sites de Design** na página de boas-vindas ignora as perguntas de entrevista apresentadas na seção **Começar.** As informações que teriam sido coletadas respondendo às perguntas da entrevista na seção **Começar** são definidas como valores padrão com essa opção. Clicando em **Sites de Design,** o designer experiente pode ignorar a entrevista inicial e alterar os valores padrão, conforme necessário, na página inicial dos **Sites** Centrais. Para concluir esta opção, pule as etapas 3 a 5 e inicie na etapa 6.

   - **Opção 3: Exibir sua topologia salva** Se você já concluiu e salvou uma topologia por meio de uso anterior da Ferramenta de Planejamento, ignore a maioria dessas etapas e comece abrindo e exibindo a topologia. Você também pode fazer alterações e atualizações na topologia, ressave-la e exportá-la para o Microsoft Excel ou o Microsoft Visio. Para concluir esta opção, pule as etapas 3 a 12 e inicie na etapa 13.

3. Click **Get Started** to begin designing your Skype for Business Server 2015 topology.

4. Responda cada seção selecionando o critério adequado para seu design e clique em **Avançar** para continuar com a próxima página do Assistente. Clique **em Voltar** para fazer alterações em páginas anteriores.

    > [!TIP]
    > Cada página possui uma descrição do critério de seleção e recomendações com base nas práticas preferidas e no planejamento de capacidade. Se você precisar de  mais detalhes, clique em Saiba mais para ler informações detalhadas da documentação de Planejamento do Skype for Business Server 2015 no site da Microsoft. Você deve ter conectividade com a Internet para acessar o site da Microsoft.

5. Selecione as opções adequadas para seu design. Após o critério inicial ser definido, uma página confirmará que sua Visão Geral dos Recursos está concluída.

6. Clique **em Design de Sites** para definir seu site central.

    > [!NOTE]
    > Cada topologia do Skype for Business Server 2015 terá pelo menos um site central. Seu design pode ter um único site central, um site central com vários sites de filial, vários sites centrais ou vários sites centrais com sites de filial associados a cada site central.

7. Em **Nome do Site,** digite o nome que identificará esse site central.

8. Em **Usuários Locais,** digite o número esperado de usuários simultâneos locais que estarão neste site central.

9. Em **Usuários Na Nuvem Homed,** digite o número esperado de usuários simultâneos online que serão homed neste site central.

10. Modifique as seleções para Colaboração Online, Usuários, Voz, Opções de Implantação Adicional ou Aplicativos do Servidor, conforme necessário.

    > [!IMPORTANT]
    > Neste ponto do design, você só pode selecionar ou limpar opções para sua implantação. No entanto, você pode configurar mais opções em uma fase posterior da Ferramenta de Planejamento. Existem também outras opções que não estão disponíveis e não podem ser desmarcadas. Além disso, você pode precisar desmarcar uma opção para desmarcar outra. Por exemplo, se você des limpar a opção  **Enterprise** Voice  em Voz, as opções Grupo de Resposta **,** Comunicado e Estacionamento de Chamada em Aplicativos do Servidor (todos os recursos do Enterprise Voice) também serão limpas.

11. Após definir um nome de site e número de usuários, clique em **Avançar**.

12. As páginas a seguir solicitam informações sobre domínios SIP, configurações de conferência, configurações de voz e infraestrutura, UM do Exchange, acesso de usuário externo, configurações de Chat Persistente, configurações do cliente, opções de localização e sites de filial. Respondas estas perguntas conforme adequado.

13. A pergunta final pergunta se você deseja criar outro site central. Se você selecionar **Sim,** a Ferramenta de Planejamento retornará à página Sites Centrais. Se você selecionar **Não,** clique **em Próximo** e, em seguida, clique em **Desenhar** para exibir a exibição de topologia global de alto nível.

14. Para exibir uma topologia existente, clique em **Exibir**.

15. Clique no arquivo .xml que representa a topologia salva anteriormente e clique em **Abrir**.

16. A Ferramenta de Planejamento exibe a página Topologia Global. Agora você pode começar a editar, atualizar ou alterar a topologia usando as ferramentas disponíveis na Ferramenta de Planejamento.

## <a name="see-also"></a>Confira também

[Editando o design](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
