---
title: Visão geral dos componentes do Loop no Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como gerenciar componentes do Loop no Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e468622d4aac30756e54127072045831374c5425
ms.sourcegitcommit: 0592f9d2696fe8c840a4ed3e7f99e55ca0c9c3e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "67418640"
---
# <a name="overview-of-loop-components-in-teams"></a>Visão geral dos componentes do Loop no Teams

Os componentes de loop no chat do Teams oferecem uma nova maneira de criar, criar e tomar decisões em conjunto. Envie um componente , como uma tabela, uma lista de tarefas ou um parágrafo, em que todos no chat podem editar embutidas e ver as alterações conforme elas são feitas. 

> [!Note]
> Os componentes de loop são o primeiro recurso [do Microsoft Loop aplicativo](https://www.microsoft.com/en-us/microsoft-loop) a ser disponibilizado no Teams. 

**Obtenha tarefas executadas mais rapidamente em conjunto.** Crie uma agenda, acompanhe os itens de ação de um grupo ou faça anotações coletivamente. Esses são apenas alguns cenários mais fáceis com componentes loop.

**Compartilhar componentes.** Nesta versão, você pode compartilhar componentes do Loop em chats diferentes do Teams. Os destinatários podem editar de onde quer que estejam e ver atualizações instantaneamente, independentemente de onde as alterações foram feitas.

**Comece no chat, compile a partir daí.** Todos os componentes criados no chat do Teams são salvos automaticamente em um arquivo no OneDrive. Portanto, você pode começar a colaborar no chat e depois mover para o arquivo no Office.com, onde você tem um espaço visual maior para edição e pode adicionar quantos componentes desejar.

Para obter informações sobre configurações de administrador para componentes loop no Teams, consulte [Gerenciar componentes loop no SharePoint](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>Clientes e plataformas

Disponível em aplicativos do Teams no Windows, Mac, Linux, iOS e Android.

## <a name="loop-components-and-fluid-files"></a>Componentes de loop e arquivos .fluid

Os componentes de loop criados no Teams são apoiados por um arquivo .fluid (será alterado para .loop em um futuro próximo) armazenado no OneDrive do criador. Ser um arquivo no OneDrive significa que os usuários podem criar, descobrir e gerenciar componentes do Loop (arquivos .fluid) tão facilmente quanto qualquer documento do Office. 

## <a name="how-are-fluid-files-stored"></a>Como os arquivos .fluid são armazenados?

Arquivos .fluid aparecem no Office.com e no OneDrive, como nas áreas Recentes e Recomendadas. Os usuários podem pesquisar conteúdo em arquivos .fluid do Office.com e do OneDrive. Arquivos .fluid podem ser restaurados para versões anteriores do OneDrive. Para criar componentes do Loop, os participantes do chat devem ter uma conta do OneDrive. Sem uma conta válida do OneDrive, os participantes do chat ainda poderão colaborar em um componente criado por outros usuários que têm uma conta válida do OneDrive, mas não podem criar suas próprias contas. 

Mover um arquivo .fluid do OneDrive para um site do SharePoint resultará em falha no carregamento do componente ao vivo no chat do Teams.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>O que acontece se o proprietário do arquivo sair da empresa?

As políticas de retenção do OneDrive se aplicam a arquivos .fluid, assim como fazem com outros conteúdos criados pelo usuário.

## <a name="how-are-fluid-files-shared"></a>Como os arquivos .fluid são compartilhados?

Os componentes de loop podem ser inseridos no chat do Teams ou copiados de um chat para outro. (Os componentes de loop ainda não têm suporte em canais.) Eles assumem como padrão as permissões existentes da organização, mas os usuários podem alterar as permissões antes de enviar para garantir que todos têm acesso.

Abrir componentes do chat do Teams Office.com oferece funcionalidade de compartilhamento na parte superior da janela, semelhante às opções de compartilhamento oferecidas para outros documentos do Office.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>E se um arquivo .fluid ficar corrompido ou danificado?

O Histórico de Versão permite examinar, restaurar ou copiar de versões anteriores do arquivo.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>Quais aplicativos podem abrir e editar arquivos .fluid?

Os arquivos .fluid só podem ser abertos como links no navegador, como Office.com e como componentes do Loop no chat do Teams. Se baixados, eles não poderão ser abertos novamente sem primeiro carregá-los de volta no OneDrive ou no SharePoint.

## <a name="does-fluid-files-support-ediscovery"></a>Os arquivos .fluid dão suporte à Descoberta Eletrônica?

Os arquivos .fluid são detectáveis, mas têm suporte limitado ao fluxo de trabalho de Descoberta Eletrônica. Atualmente, os arquivos .fluid são armazenados no OneDrive do criador e estão disponíveis para pesquisa e coleta na Descoberta Eletrônica (Standard) e na Descoberta Eletrônica (Premium). No entanto, eles não são renderizados em versão prévia e o formato de exportação para revisão não é consumível por ferramentas existentes. Para exibir o conteúdo exportado, carregue-os em qualquer OneDrive. Se desejar, você poderá desabilitar temporariamente essas experiências, conforme descrito na [seção Gerenciamento de configurações](/sharepoint/manage-loop-components#settings-management) .

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>Se o Loop estiver desabilitado na opção de administrador, qual será a experiência do usuário?

Se você desabilitar essas experiências conforme descrito na seção [Gerenciamento](/sharepoint/manage-loop-components#settings-management) de Configurações, as seguintes alterações de experiência serão aplicadas:

- O ponto de entrada de criação/inserção no sistema de mensagens do Teams ficará oculto. Os usuários não poderão criar novos arquivos .fluid.
- As mensagens existentes que anteriormente seriam renderizadas como um componente loop interativo serão renderizadas como um hiperlink "Componente loop". Nenhum conteúdo interativo será exibido no Teams.
- Quando um usuário final clica no hiperlink "Componente loop" ou navega para um arquivo .fluid no OneDrive for Business e clica para abrir, ele abrirá o arquivo em uma guia separada do navegador, mas os usuários finais não poderão editar o arquivo.

## <a name="known-issues"></a>Problemas conhecidos

- Com as permissões de arquivo padrão do locatário definidas para Pessoas específicas *(somente* as pessoas especificadas pelo usuário), copiar o link para o componente Loop e colá-lo em outro chat exige que o remetente use a caixa de diálogo de permissões e adicione os destinatários na opção Pessoas específicas para conceder acesso corretamente.
- Com permissões de arquivo padrão de locatário definidas como Pessoas específicas *(somente* as pessoas especificadas pelo usuário), a criação de um componente ao vivo no chat em grupo com mais de 20 membros exigirá que o remetente selecione manualmente as opções de permissão para o componente.
- A pesquisa de componentes loop na pesquisa do Teams retornará um link para o componente no office.com, não a mensagem de chat em si.
- Os componentes de loop são desabilitados em chats federados.
- Os convidados não poderão colaborar em um componente ao vivo que é compartilhado com eles por meio do Link de Compartilhamento da Empresa. Defina permissões para **Pessoas atualmente neste chat** para compartilhar componentes com convidados.
- Não há suporte para componentes de loop nos canais do Teams.
- Os componentes de loop no chat não serão carregados somente se o arquivo tiver sido movido para uma biblioteca diferente. Se o arquivo for movido para uma pasta diferente, ele continuará a ser carregado no chat.
