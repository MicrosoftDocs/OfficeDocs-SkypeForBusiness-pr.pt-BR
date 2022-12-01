---
title: Visão geral dos componentes loop no Teams
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
description: Saiba como gerenciar componentes loop no Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1405464a3eb963d55c357b5fcc165c67a143e5e1
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198543"
---
# <a name="overview-of-loop-components-in-teams"></a>Visão geral dos componentes loop no Teams

Os componentes de loop no chat do Teams oferecem uma nova maneira de idear, criar e tomar decisões juntos. Enviar um componente – como uma tabela, uma lista de tarefas ou um parágrafo – em que todos no chat podem editar de forma embutida e ver as alterações conforme são feitas. 

> [!Note]
> Componentes de loop é o primeiro recurso do [aplicativo Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) a ficar disponível no Teams. 

**Faça tarefas mais rápidas juntos.** Faça uma agenda de origem coletiva, acompanhe os itens de ação de um grupo ou faça anotações coletivamente. Esses são apenas alguns cenários facilitado com componentes loop.

**Compartilhar componentes.** Nesta versão, você pode compartilhar componentes loop em chats diferentes do Teams. Os destinatários podem editar de onde quer que estejam e ver atualizações instantaneamente, não importa onde as alterações foram feitas.

**Comece no chat, crie a partir daí.** Cada componente criado no chat do Teams é salvo automaticamente em um arquivo no OneDrive. Portanto, você pode começar a colaborar no chat e, posteriormente, passar para o arquivo no Office.com, em que você tem um espaço visual maior para edição e pode adicionar quantos componentes quiser.

Para obter informações sobre configurações de administrador para componentes loop no Teams, consulte [Gerenciar componentes de loop no SharePoint](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>Clientes e plataformas

Disponível em aplicativos do Teams no Windows, Mac, Linux, iOS e Android.

## <a name="loop-components-and-fluid-files"></a>Componentes de loop e arquivos .fluid

Os componentes de loop criados no Teams são apoiados por um arquivo .fluid (será alterado para .loop em um futuro próximo) armazenado no OneDrive do criador. Ser um arquivo no OneDrive significa que os usuários podem criar, descobrir e gerenciar componentes loop (.arquivos fluidos) tão facilmente quanto qualquer documento do Office. 

## <a name="how-are-fluid-files-stored"></a>Como os arquivos .fluid são armazenados?

Os arquivos .fluid aparecem no Office.com e no OneDrive, como nas áreas recente e recomendada. Os usuários podem pesquisar conteúdo em arquivos .fluid do Office.com e do OneDrive. Os arquivos .fluid podem ser restaurados para versões anteriores do OneDrive. Para criar componentes de loop, os participantes do chat devem ter uma conta do OneDrive. Sem uma conta válida do OneDrive, os participantes do chat ainda podem colaborar em um componente criado por outros usuários que têm uma conta válida do OneDrive, mas não podem criar a sua própria. 

Mover um arquivo .fluid do OneDrive para um site do SharePoint resultará na falha no carregamento do componente ao vivo no chat do Teams.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>O que acontecerá se o proprietário do arquivo deixar a empresa?

As políticas de retenção do OneDrive se aplicam a arquivos .fluid, assim como fazem com outros conteúdos criados pelo usuário.

## <a name="how-are-fluid-files-shared"></a>Como os arquivos .fluid são compartilhados?

Os componentes de loop podem ser inseridos no chat do Teams ou copiados de um chat para outro. (Os componentes de loop ainda não têm suporte em canais.) Eles são padrão para as permissões existentes da organização, mas os usuários podem alterar permissões antes de enviar para garantir que todos tenham acesso.

Abrir componentes do chat do Teams no Office.com oferece funcionalidade de compartilhamento na parte superior da janela, semelhante às opções de compartilhamento oferecidas para outros documentos do Office.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>E se um arquivo .fluid ficar corrompido ou danificado?

O Histórico de Versão permite que você examine, restaure ou copie as versões anteriores do arquivo.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>Quais aplicativos podem abrir e editar arquivos .fluid?

Os arquivos .fluid só podem ser abertos como links no navegador, como Office.com e como componentes loop no chat do Teams. Se baixados, eles não poderão ser abertos novamente sem primeiro carregá-los de volta para o OneDrive ou SharePoint.

## <a name="does-fluid-files-support-ediscovery"></a>Os arquivos .fluid dão suporte à descoberta eletrônica?

Os arquivos .fluid são detectáveis, mas têm suporte limitado ao fluxo de trabalho de descoberta eletrônica. Atualmente, os arquivos .fluid são armazenados no OneDrive do criador e estão disponíveis para pesquisa e coleção em eDiscovery (Standard) e eDiscovery (Premium). No entanto, eles não renderizam em versão prévia e o formato de exportação para revisão não é consumível pelas ferramentas existentes. Para exibir o conteúdo exportado, carregue-os em qualquer OneDrive. Se desejar, você poderá desabilitar temporariamente essas experiências conforme descrito na seção [Gerenciamento de Configurações](/sharepoint/manage-loop-components#settings-management) .

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>Se Loop estiver desabilitado da opção de administrador, qual será a experiência do usuário?

Se você desabilitar essas experiências conforme descrito na seção [Gerenciamento de Configurações, as seguintes](/sharepoint/manage-loop-components#settings-management) alterações de experiência serão aplicadas:

- O ponto de entrada criar/inserir dentro das mensagens do Teams será oculto. Os usuários não poderão criar novos arquivos .fluid.
- As mensagens existentes que anteriormente seriam renderizadas como um componente do Loop interativo serão renderizadas como um hiperlink "Componente loop". Nenhum conteúdo interativo será exibido no Teams.
- Quando um usuário final clica no hiperlink "Componente loop" ou navega até um arquivo .fluid em OneDrive for Business e clica para abrir, ele abrirá o arquivo em uma guia separada do navegador. Os usuários finais ainda poderão editar o arquivo.

## <a name="known-issues"></a>Problemas conhecidos

- Com as permissões de arquivo padrão do locatário definidas como *pessoas específicas* (apenas as pessoas especificadas pelo usuário), copiar o link para o componente Loop e colá-lo em outro chat requer que o remetente use a caixa de diálogo permissões e adicione os destinatários na opção Pessoas específicas para conceder acesso corretamente.
- Com as permissões de arquivo padrão do locatário definidas como *pessoas específicas* (apenas as pessoas especificadas pelo usuário), a criação de um componente dinâmico no chat em grupo com mais de 20 membros exigirá que o remetente selecione manualmente as opções de permissão para o componente.
- A pesquisa de componentes loop na pesquisa do Teams retornará um link para o componente em office.com, não a mensagem de chat em si.
- Os componentes de loop são desabilitados em chats federados.
- Os convidados não poderão colaborar em um componente ao vivo compartilhado com eles por meio do Link de Compartilhamento da Empresa. Defina permissões para **Pessoas atualmente neste chat** para compartilhar componentes com convidados.
- Não há suporte para componentes de loop nos canais do Teams.
- Os componentes de loop no chat não serão carregados somente se o arquivo for movido para uma biblioteca diferente. Se o arquivo for movido para uma pasta diferente, ele continuará a ser carregado no chat.
