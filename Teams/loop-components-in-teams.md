---
title: Visão geral dos Loop componentes no Teams
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
description: Saiba como gerenciar componentes Loop no Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fb436ef2e8b32f737fcfa10823b54dc0e6a7cca
ms.sourcegitcommit: 07abd8fdb653e57a839ded72620d0179049f25dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "66088577"
---
# <a name="overview-of-loop-components-in-teams"></a>Visão geral dos Loop componentes no Teams

Loop componentes Teams chat oferecem uma nova maneira de criar, criar e tomar decisões juntos. Envie um componente , como uma tabela, uma lista de tarefas ou um parágrafo, em que todos no chat podem editar embutidas e ver as alterações conforme elas são feitas. 

> [!Note]
> Loop componentes é o primeiro recurso do [aplicativo Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) a ficar disponível no Teams. 

**Obtenha tarefas executadas mais rapidamente em conjunto.** Crie uma agenda, acompanhe os itens de ação de um grupo ou faça anotações coletivamente. Esses são apenas alguns cenários mais fáceis com Loop componentes.

**Compartilhar componentes.** Nesta versão, você pode compartilhar Loop componentes em diferentes Teams chats. Os destinatários podem editar de onde quer que estejam e ver atualizações instantaneamente, independentemente de onde as alterações foram feitas.

**Comece no chat, compile a partir daí.** Todos os componentes criados Teams chat são salvos automaticamente em um arquivo OneDrive. Portanto, você pode começar a colaborar no chat e depois ir para o arquivo, onde você tem um espaço visual maior para edição e pode adicionar quantos componentes desejar.

Para obter informações sobre configurações de administrador Loop componentes do Teams, consulte [Gerenciar Loop componentes no SharePoint](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>Clientes e plataformas

Disponível em Teams aplicativos Windows, Mac, Linux, iOS e Android.

## <a name="loop-components-and-fluid-files"></a>Loop componentes e arquivos .fluid

Loop componentes criados no Teams são apoiados por um arquivo .fluid armazenado no OneDrive. Ser um arquivo no OneDrive significa que os usuários podem criar, descobrir e gerenciar componentes Loop (arquivos .fluid) tão facilmente quanto qualquer Office documento. 

## <a name="how-are-fluid--files-stored"></a>Como os arquivos .fluid são armazenados?

Os arquivos .fluid aparecem Office.com e OneDrive, como nas áreas Recentes e Recomendadas. Os usuários podem pesquisar conteúdo em arquivos .fluid Office.com e OneDrive. Arquivos .fluid podem ser restaurados para versões anteriores do OneDrive. Para criar Loop componentes de chat, os participantes devem ter uma OneDrive conta. Sem uma conta OneDrive válida, os participantes do chat ainda poderão colaborar em um componente criado por outros usuários que têm uma conta OneDrive válida, mas não podem criar suas próprias. 

Mover um arquivo .fluid de OneDrive para um site de SharePoint resultará em falha no carregamento do componente ao vivo Teams chat.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>O que acontece se o proprietário do arquivo sair da empresa?

OneDrive políticas de retenção se aplicam a arquivos .fluid, assim como fazem com outros conteúdos criados pelo usuário.

## <a name="how-are-fluid-files-shared"></a>Como os arquivos .fluid são compartilhados?

Loop componentes podem ser inseridos Teams chat ou copiados de um chat para outro. (Loop componentes ainda não têm suporte em canais.) Eles assumem como padrão as permissões existentes da organização, mas os usuários podem alterar as permissões antes de enviar para garantir que todos têm acesso.

Abrir componentes Teams chat no Office.com oferece funcionalidade de compartilhamento na parte superior da janela, semelhante às opções de compartilhamento oferecidas para outros Office documentos.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>E se um arquivo .fluid ficar corrompido ou danificado?

O Histórico de Versão permite que você examine e copie de versões anteriores do arquivo.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>Quais aplicativos podem abrir e editar arquivos .fluid?

Os arquivos .fluid só podem ser abertos como links no navegador, como Office.com e como componentes Loop no Teams chat. Se baixados, eles não poderão ser abertos novamente sem primeiro carregá-los de volta para OneDrive ou SharePoint.

## <a name="does-fluid-files-support-ediscovery"></a>Os arquivos .fluid dão suporte à Descoberta Eletrônica?

Os arquivos .fluid são detectáveis, mas têm suporte limitado ao fluxo de trabalho de Descoberta Eletrônica. Atualmente, os arquivos .fluid são armazenados no OneDrive do criador e estão disponíveis para pesquisa e coleta na Descoberta Eletrônica (Standard) e na Descoberta Eletrônica (Premium). No entanto, eles não são renderizados em versão prévia e o formato de exportação para revisão não é consumível por ferramentas existentes. Para exibir o conteúdo exportado, carregue-os em qualquer OneDrive. Se desejar, você poderá desabilitar temporariamente essas experiências, conforme descrito na seção [Configurações gerenciamento](/sharepoint/manage-loop-components#settings-management).

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>Se Loop estiver desabilitado na opção de administrador, qual será a experiência do usuário?

Se você desabilitar essas experiências conforme descrito na [seção Configurações de gerenciamento](/sharepoint/manage-loop-components#settings-management), as seguintes alterações de experiência serão aplicadas:

- O ponto de entrada de criação/inserção dentro Teams mensagens serão ocultadas. Os usuários não poderão criar novos arquivos .fluid.
- As mensagens existentes que anteriormente seriam renderizadas como um componente Loop interativo serão renderizadas como um hiperlink "Loop componente". Nenhum conteúdo interativo será exibido no Teams.
- Quando um usuário final clica no hiperlink "componente Loop" ou navega para um arquivo .fluid no OneDrive for Business e clica para abrir, ele abrirá o arquivo em uma guia separada do navegador, mas os usuários finais não poderão editar o arquivo.

## <a name="known-issues"></a>Problemas conhecidos

- Loop componentes no chat não podem ser editados por meio Aplicativo do Office ao usar Teams no Android.
- Se as permissões de arquivo padrão do locatário forem definidas como Pessoas específicas *(somente* as pessoas especificadas pelo usuário) e o remetente remover alguns  usuários da lista Pessoas específicas na caixa de diálogo de permissões ao criar um componente, esses usuários ainda poderão ter acesso ao conteúdo.
- Com permissões de arquivo padrão de locatário definidas para Pessoas específicas *(somente* as pessoas especificadas pelo usuário), copiar o link para o componente dinâmico e colar em outro chat exige que o remetente use a caixa de diálogo permissões e adicione os destinatários na opção Pessoas específicas para conceder acesso corretamente.
- Com permissões de arquivo padrão de locatário definidas como Pessoas específicas *(somente* as pessoas especificadas pelo usuário), a criação de um componente ao vivo no chat em grupo com mais de 20 membros exigirá que o remetente selecione manualmente as opções de permissão para o componente.
- A pesquisa Loop componentes Teams pesquisa retornará um link para o componente no office.com, não a mensagem de chat em si.
- Loop componentes estão desabilitados em chats federados.
- Os convidados B2B não poderão colaborar em um componente ao vivo que é compartilhado com eles por meio do Link de Compartilhamento da Empresa. Defina permissões para **Pessoas atualmente neste chat** para compartilhar componentes com convidados B2B.
- Loop componentes não têm suporte em Teams canais.
- Loop componentes no chat não serão carregados somente se o arquivo tiver sido movido para uma biblioteca diferente. Se o arquivo for movido para uma pasta diferente, ele continuará a ser carregado no chat.
