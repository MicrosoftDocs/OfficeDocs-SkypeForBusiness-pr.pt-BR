---
title: Configurar o ServiceNow para Salas do Teams
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Saiba mais sobre como configurar o ServiceNow no portal Salas do Teams Pro Management
f1keywords: ''
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
ms.openlocfilehash: e437a27b6c1ba04b76cd71aa70c9913acf78c45d
ms.sourcegitcommit: 64c01699022b47fdfec8dc6e2ca279e57eae3baa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68243722"
---
# <a name="configure-servicenow-for-teams-rooms"></a>Configurar o ServiceNow para Salas do Teams

Este artigo descreve os pré-requisitos e as etapas para configurar o ambiente do ServiceNow no portal Salas do Teams Pro Management.

## <a name="watch-microsoft-teams-rooms-pro-management--service-now-integration"></a>Assista: Salas do Microsoft Teams Pro Management — Integração do Service Now

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ZK4B]


### <a name="teams-rooms-prerequisites"></a>Salas do Teams pré-requisitos

- Você deve ter uma função de Administrador de Serviços atribuída. Para obter mais informações, consulte [Controle de acesso baseado em função com o Salas do Microsoft Teams Pro Management](microsoft-teams-rooms-premium-rbac.md).

### <a name="servicenow-prerequisites"></a>Pré-requisitos do ServiceNow

- Uma entrada de Autorização Básica ou uma entrada [OAuth](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) . Para obter mais informações, consulte [Criando credenciais](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) no ServiceNow.
- Uma instância do ServiceNow e seu nome de host de instância e URI de API
- Uma função de incident_manager ou superior
- Uma versão de software do ServiceNow que dá suporte à API de Tabela

## <a name="configure-your-environment"></a>Configurar seu ambiente

A maneira como seu ambiente é configurado é altamente personalizável e dependerá das necessidades da sua organização. As etapas a seguir explicam como copiar sua configuração existente no ServiceNow para o portal Salas do Teams Pro Management.

1. Abra a instância do ServiceNow que você deseja copiar. Você precisará fazer referência a isso ao concluir o formulário de configuração no portal Salas do Teams Pro Management.
2. Em uma nova guia do navegador, acesse o [portal de gerenciamento Salas do Teams Pro e](https://portal.rooms.microsoft.com/) vá para **Configurações**. Em seguida, **selecione ServiceNow** no menu de navegação esquerdo para abrir o formulário de configuração.
3. Selecione um método de autenticação para entrar e insira o Host da Instância do ServiceNow e o URI da API.
4. Todos os itens necessários na coluna Campo do ServiceNow da seção Mapeamento de Campo devem ser preenchidos previamente. A tabela a seguir contém cada campo do ServiceNow e seu campo Salas do Microsoft Teams correspondente. Conclua a ação para cada linha da seção Mapeamento de Campo. Para obter definições de cada campo do ServiceNow, consulte as [definições de campo do ServiceNow](#servicenow-field-definitions).

| Campo ServiceNow | Salas do Microsoft Teams campo | Ação |
| --- | --- | --- |
| short_description | Descrição do incidente | Nenhuma ação é necessária. O Salas do Teams campo é preenchido automaticamente. |
| Descrição | Primeira Mensagem | Nenhuma ação é necessária. O Salas do Teams campo é preenchido automaticamente. |
| assignment_group | Grupo de sala | Copie o assignment_group em sua instância do ServiceNow e cole-o no campo de valor do ServiceNow no formulário de configuração. Se você tiver mais de um assignment_group, selecione **Adicionar Grupo de** Sala para cada valor personalizado adicional. |
| Gravidade | Anéis | A severidade é um valor personalizado no ServiceNow. É o quarto item na segunda coluna da instância do ServiceNow. Copie o valor e cole-o no campo de valor do ServiceNow no formulário de configuração. Se você tiver mais de um valor de severidade, selecione **Adicionar Anel** para cada valor personalizado adicional. |
| Comentários (opcional) | Valor personalizado* | Para adicionar um campo de comentários ao formulário de configuração, selecione **Adicionar** na parte superior da seção de mapeamento de campo. Copie o valor do comentário em sua instância do ServiceNow e cole-o no campo ServiceNow no formulário de configuração. Atribua a ele um campo sala do Microsoft Teams no menu suspenso e copie e cole o valor do ServiceNow. |
| estado (resolvido) | Valor personalizado* | Copie o estado de resolução da instância do ServiceNow e cole-o no campo de valor do ServiceNow no formulário de configuração. |
| close_code | Valor personalizado* | Na guia **Informações de Resolução** da instância do ServiceNow, copie o código de fechamento e cole-o no campo de valor do ServiceNow no formulário de configuração. |

*Selecione valores personalizados no menu suspenso

>[!NOTE]
>Se você não conseguir localizar seus valores personalizados, entre em contato com o administrador do ServiceNow.

Para adicionar campos obrigatórios adicionais à seção Resolver Incidente, selecione **Adicionar**.

## <a name="test-and-enable"></a>Testar e habilitar

Depois de concluir o formulário de configuração, selecione **Testar** na parte inferior da página. O teste é necessário para enviar sua configuração.

Depois que o teste for aprovado com êxito, selecione **Enviar** para salvar suas alterações. Quando estiver pronto para habilitar o ServiceNow para sua organização, alterne a opção Deseja habilitar o **ServiceNow?** para **Ativado**.

## <a name="servicenow-field-definitions"></a>Definições de campo do ServiceNow

- **short_description**: o campo de descrição curta no ServiceNow é um valor alfanumérico breve de 160 caracteres que fornece um resumo do incidente. A descrição curta é equivalente à descrição do incidente no portal Salas do Teams Pro Management.

- **descrição**: o campo de descrição no ServiceNow é o primeiro valor no histórico de conversas de um incidente do ServiceNow. A descrição é equivalente à Primeira mensagem no portal Salas do Teams Pro Management.

- **assignment_group**: o campo de grupo de atribuição no ServiceNow é usado para organizar incidentes. Os grupos de atribuição são equivalentes aos grupos de sala no portal Salas do Teams Pro Management. Por padrão, há um grupo de sala e mais podem ser adicionados. Você decide quantos grupos existem e como agrupar seus incidentes. Por exemplo, você pode optar por organizar seus incidentes por local.

- **severidade**: o campo de severidade no ServiceNow é usado para organizar incidentes por prioridade. Os valores que designam prioridade são personalizáveis. A severidade é equivalente ao campo Anel no portal Salas do Teams Pro Management. Para personalizar anéis no portal Salas do Teams Pro Management, acesse **Atualizações** no menu de navegação à esquerda. Em seguida, vá para **a guia Anéis** e selecione **Adicionar anel**.

- **comentários**: Comentários é um campo opcional no ServiceNow que é usado para incluir campos obrigatórios personalizados de sua instância do ServiceNow em sua configuração do portal Salas do Teams Pro Management. O equivalente de comentários é um valor personalizado no portal Salas do Teams Pro Management.

- **estado (resolvido)**: o campo de estado (resolvido) no ServiceNow é usado para designar como um incidente foi resolvido e é necessário para fechar um incidente. O valor de estado (resolvido) é personalizável. O equivalente de estado (resolvido) é um valor personalizado no portal Salas do Teams Pro Management.

- **close_code**: um código de fechamento deve ser atribuído a um incidente depois que ele for completamente resolvido. Esse valor é personalizável no ServiceNow. O equivalente ao código de fechamento é um valor personalizado no portal Salas do Teams Pro Management.
