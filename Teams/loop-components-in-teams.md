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
description: Saiba como gerenciar componentes do Loop Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 175b7f4bf8d181ae7e66edb255bd32dd40bb2fa1
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518973"
---
# <a name="overview-of-loop-components-in-teams"></a>Visão geral dos componentes do Loop no Teams

Os componentes de loop Teams chat oferecem uma nova maneira de idear, criar e tomar decisões juntos. Envie um componente - como uma tabela, uma lista de tarefas ou um parágrafo - onde todos no chat podem editar em linha e ver alterações à medida que são feitas. 

> [!Note]
> Componentes de loop é o primeiro recurso do [aplicativo Do Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) a ser disponibilizado no Teams. 

**Realizar tarefas mais rápidas juntos.** Origem de uma agenda, controle os itens de ação de um grupo ou tome anotações coletivamente. Esses são apenas alguns cenários mais fáceis com componentes do Loop.

**Compartilhar componentes.** Nesta versão, você pode compartilhar componentes do Loop em diferentes Teams chats. Os destinatários podem editar de onde quer que estejam e ver atualizações instantaneamente, independentemente de onde as alterações foram feitas.

**Comece no chat, crie a partir daí.** Todos os componentes que você cria Teams chat são salvos automaticamente em um arquivo em OneDrive. Portanto, você pode começar a colaborar no chat e depois mover para o arquivo, onde você tem um espaço visual maior para edição e pode adicionar quantos componentes quiser.

## <a name="clients-and-platforms"></a>Clientes e plataformas

Disponível em Teams aplicativos em Windows, Mac, Linux, iOS e Android.

## <a name="loop-components-and-fluid-files"></a>Componentes de loop e arquivos .fluid

Os componentes de loop criados Teams são respaldados por um arquivo .fluid armazenado no OneDrive. Ser um arquivo no OneDrive significa que os usuários podem criar, descobrir e gerenciar componentes do Loop (arquivos.fluidos) tão facilmente quanto qualquer Office documento. Os arquivos .fluid funcionam com recursos de governança de dados, como Descoberta eDiscovery, auditoria, relatórios e retenção legal.

## <a name="how-are-fluid--files-stored"></a>Como os arquivos .fluid são armazenados?

Os arquivos .fluid aparecem em Office.com e OneDrive, como nas áreas Recente e Recomendada. Os usuários podem pesquisar conteúdo em arquivos .fluid em Office.com e OneDrive. Os arquivos .fluid podem ser restaurados para versões anteriores OneDrive. Para criar componentes do Loop, os participantes de chat devem ter uma OneDrive de usuário. Sem uma conta OneDrive, os participantes de chat ainda poderão colaborar em um componente criado por outros usuários que tenham uma conta OneDrive válida, mas não podem criar suas próprias. 

A movimentação de um arquivo .fluid OneDrive para um site SharePoint resultará em falha no carregamento do componente ao vivo Teams chat.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>O que acontece se o proprietário do arquivo sair da empresa?

OneDrive de retenção se aplicam a arquivos .fluid assim como fazem com outros conteúdos criados pelo usuário.

## <a name="how-are-fluid-files-shared"></a>Como os arquivos .fluid são compartilhados?

Os componentes de loop podem ser inseridos Teams chat ou copiados de um chat para outro. (Os componentes do loop ainda não têm suporte em canais.) Eles são padrão para as permissões existentes da organização, mas os usuários podem alterar as permissões antes de enviar para garantir que todos tenham acesso.

Abrir componentes Teams chat no Office.com oferece funcionalidade de compartilhamento na parte superior da janela, semelhante às opções de compartilhamento oferecidas para outros documentos Office.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>E se um arquivo .fluid ficar corrompido ou danificado?

Histórico de versão permite que você revise e copie de versões anteriores do arquivo.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>Quais aplicativos podem abrir e editar arquivos .fluid?

Os arquivos .fluid só podem ser abertos como links no navegador, como Office.com e como componentes do Loop no Teams chat. Se baixados, eles não poderão ser abertos novamente sem primeiro enviá-los de volta para OneDrive ou SharePoint.

## <a name="known-issues"></a>Problemas conhecidos

- Os componentes de loop no chat não podem ser editados por Aplicativo do Office ao usar Teams no Android.
- Se as permissões de arquivo padrão do locatário são definidas como Pessoas específicas *(somente* as pessoas que o usuário especifica) e o remetente remove alguns  usuários da lista De pessoas específicas na caixa de diálogo permissões ao criar um componente, esses usuários ainda podem ter acesso ao conteúdo.
- Com permissões de arquivo padrão de locatário definidas como Pessoas específicas *(somente* as pessoas que o usuário especifica), copiar link para componentes ao vivo e colar em outro chat exige que o remetente use a caixa de diálogo permissões e adicione os destinatários na opção Pessoas específicas para conceder acesso corretamente.
- Com permissões de arquivo padrão de locatário definidas como Pessoas específicas *(somente* as pessoas que o usuário especifica), a criação de um componente ao vivo no chat em grupo com mais de 20 membros exigirá que o remetente selecione manualmente as opções de permissão para o componente.
- Pesquisar componentes do Loop Teams pesquisa retornará um link para o componente office.com, não a mensagem de chat em si.
- Os componentes do loop são desabilitados em chats federados.
- Os convidados B2B não poderão colaborar em um componente ao vivo compartilhado com eles por meio *de links pessoas* em sua organização, a menos que o locatário desempate uma opção de acesso externo para permitir que os convidados B2B tenham o mesmo nível de acesso que os membros do locatário. Para obter mais informações, consulte [Configure B2B external collaboration settings](/azure/active-directory/external-identities/delegate-invitations#configure-b2b-external-collaboration-settings).
- Os componentes de loop não são suportados Teams canais.
- Os componentes de loop no chat não serão carregados somente se o arquivo tiver sido movido para uma biblioteca diferente. Se o arquivo for movido para uma pasta diferente, ele continuará a ser carregado no chat.

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar componentes do Loop em SharePoint](/sharepoint/manage-loop-components)
