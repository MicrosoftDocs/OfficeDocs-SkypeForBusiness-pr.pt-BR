---
title: Visão geral dos componentes do Loop Teams
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
description: Saiba como gerenciar componentes do Loop Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f9ca97a0088c703dc482d69406a9e9c2c8b2a22
ms.sourcegitcommit: 71edff2670367082312de59c4e21775682871418
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2022
ms.locfileid: "63043369"
---
# <a name="overview-of-loop-components-in-teams"></a>Visão geral dos componentes do Loop Teams

Os componentes de loop Teams chat oferecem uma nova maneira de idear, criar e tomar decisões juntos. Envie um componente - como uma tabela, uma lista de tarefas ou um parágrafo - onde todos no chat podem editar em linha e ver alterações à medida que são feitas. 

> [!Note]
> Componentes de loop é o primeiro recurso do [aplicativo Do Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) a ser disponibilizado Teams. 

**Realizar tarefas mais rápidas juntos.** Origem de uma agenda, controle os itens de ação de um grupo ou tome anotações coletivamente. Esses são apenas alguns cenários mais fáceis com componentes do Loop.

**Compartilhar componentes.** Nesta versão, você pode compartilhar componentes do Loop em diferentes Teams chats. Os destinatários podem editar de onde quer que estejam e ver atualizações instantaneamente, independentemente de onde as alterações foram feitas.

**Comece no chat, crie a partir daí.** Todos os componentes que você cria Teams chat são salvos automaticamente em um arquivo em OneDrive. Portanto, você pode começar a colaborar no chat e depois mover para o arquivo, onde você tem um espaço visual maior para edição e pode adicionar quantos componentes quiser.

Para obter informações sobre configurações de administrador para componentes do Loop Teams, consulte [Manage Loop components in SharePoint](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>Clientes e plataformas

Disponível em Teams aplicativos em Windows, Mac, Linux, iOS e Android.

## <a name="loop-components-and-loop-files"></a>Componentes de loop e arquivos .loop

Os componentes de loop criados Teams são respaldados por um arquivo .loop armazenado no OneDrive. Ser um arquivo em OneDrive significa que os usuários podem criar, descobrir e gerenciar componentes do Loop (arquivos.loop) tão facilmente quanto qualquer documento Office. Os arquivos .loop funcionam com recursos de governança de dados, como Descoberta eDiscovery, auditoria, relatórios e ressarcimento legal.

## <a name="how-are-loop--files-stored"></a>Como os arquivos .loop são armazenados?

Os arquivos .loop aparecem em Office.com e OneDrive, como nas áreas Recente e Recomendada. Os usuários podem pesquisar conteúdo em arquivos .loop de Office.com e OneDrive. Os arquivos .loop podem ser restaurados para versões anteriores OneDrive. Para criar componentes do Loop, os participantes de chat devem ter uma OneDrive de usuário. Sem uma conta OneDrive, os participantes de chat ainda poderão colaborar em um componente criado por outros usuários que tenham uma conta OneDrive válida, mas não podem criar suas próprias. 

Mover um arquivo .loop de OneDrive para um site de SharePoint resultará em falha ao carregar o componente ao vivo Teams chat.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>O que acontece se o proprietário do arquivo sair da empresa?

OneDrive de retenção se aplicam a arquivos .loop da mesma forma que fazem com outros conteúdos criados pelo usuário.

## <a name="how-are-loop-files-shared"></a>Como os arquivos .loop são compartilhados?

Os componentes de loop podem ser inseridos Teams chat ou copiados de um chat para outro. (Os componentes do loop ainda não têm suporte em canais.) Eles são padrão para as permissões existentes da organização, mas os usuários podem alterar as permissões antes de enviar para garantir que todos tenham acesso.

Abrir componentes Teams chat no Office.com oferece funcionalidade de compartilhamento na parte superior da janela, semelhante às opções de compartilhamento oferecidas para outros documentos Office.

## <a name="what-if-a-loop-file-becomes-corrupted-or-damaged"></a>E se um arquivo .loop ficar corrompido ou danificado?

Histórico de versão permite que você revise e copie de versões anteriores do arquivo.

## <a name="what-apps-can-open-and-edit-loop-files"></a>Quais aplicativos podem abrir e editar arquivos .loop?

Os arquivos .loop só podem ser abertos como links no navegador, como Office.com e como componentes do Loop no Teams chat. Se baixados, eles não poderão ser abertos novamente sem primeiro carregar de volta para OneDrive ou SharePoint.

## <a name="known-issues"></a>Problemas conhecidos

- Os componentes de loop no chat não podem ser editados por Aplicativo do Office ao usar Teams no Android.
- Se as permissões de arquivo padrão do locatário são definidas como Pessoas específicas *(somente* as pessoas que o usuário especifica) e o remetente remove alguns  usuários da lista De pessoas específicas na caixa de diálogo permissões ao criar um componente, esses usuários ainda podem ter acesso ao conteúdo.
- Com permissões de arquivo padrão de locatário definidas como Pessoas específicas *(somente* as pessoas que o usuário especifica), copiar link para componentes ao vivo e colar em outro chat exige que o remetente use a caixa de diálogo permissões e adicione os destinatários na opção Pessoas específicas para conceder acesso corretamente.
- Com permissões de arquivo padrão de locatário definidas como Pessoas específicas *(somente* as pessoas que o usuário especifica), a criação de um componente ao vivo no chat em grupo com mais de 20 membros exigirá que o remetente selecione manualmente as opções de permissão para o componente.
- Pesquisar componentes do Loop Teams pesquisa retornará um link para o componente no office.com, não a mensagem de chat em si.
- Os componentes do loop são desabilitados em chats federados.
- Os convidados B2B não poderão colaborar em um componente ao vivo compartilhado com eles por meio do Link de Compartilhamento da Empresa. Definir permissões para **pessoas atualmente neste chat** para compartilhar componentes com convidados B2B.
- Os componentes de loop não são suportados Teams canais.
- Os componentes de loop no chat não serão carregados somente se o arquivo tiver sido movido para uma biblioteca diferente. Se o arquivo for movido para uma pasta diferente, ele continuará a ser carregado no chat.