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
description: Saiba mais sobre como configurar o ServiceNow no portal de Gerenciamento de Salas Teams Pro
f1keywords: ''
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
ms.openlocfilehash: 2166332df2c4ea388256d32a9dbc35a709042041
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046850"
---
# <a name="configure-servicenow-for-teams-rooms"></a>Configurar o ServiceNow para Salas do Teams

Este artigo descreve os pré-requisitos e as etapas para configurar o ambiente do ServiceNow no portal de Gerenciamento de Salas Teams Pro.

## <a name="watch-microsoft-teams-rooms-pro-management--service-now-integration"></a>Assista: Gerenciamento de Salas Microsoft Teams Pro – Integração do Service Now

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ZK4B]


### <a name="teams-rooms-prerequisites"></a>Salas do Teams pré-requisitos

- Você deve ter uma função de Administrador de Serviço atribuída. Para obter mais informações, consulte [Controle de acesso baseado em função com Salas Microsoft Teams Pro Gerenciamento](rooms-pro-rbac.md).

### <a name="servicenow-prerequisites"></a>Pré-requisitos do ServiceNow

- Uma entrada de Autorização Básica, OU uma entrada [OAuth](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) . Para obter mais informações, consulte [Criando credenciais](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) no ServiceNow.
- Uma instância do ServiceNow e seu nome de host de instância e URI de API
- Uma função de incident_manager ou superior
- Uma versão de software do ServiceNow que dá suporte à API de Tabela

## <a name="configure-your-environment"></a>Configurar seu ambiente

A forma como seu ambiente está configurado é altamente personalizável e dependerá das necessidades da sua organização. As etapas a seguir explicam como copiar sua configuração existente no ServiceNow para o portal de Gerenciamento de Salas Teams Pro.

1. Abra a instância do ServiceNow que você deseja copiar. Você precisará fazer referência a isso ao concluir o formulário de configuração no portal de Gerenciamento de Salas Teams Pro.
2. Em uma nova guia do navegador, acesse o [portal de Gerenciamento de Salas Teams Pro](https://portal.rooms.microsoft.com/) e acesse **Configurações**. Em seguida, selecione **ServiceNow** no menu de navegação esquerdo para abrir o formulário de configuração.
3. Selecione um método de autenticação para entrar e insira o Host da Instância do ServiceNow e o URI da API.
4. Todos os itens necessários na coluna ServiceNow Field da seção Mapeamento de Campo devem ser pré-preenchidos. A tabela abaixo contém cada campo ServiceNow e seu campo de Salas do Microsoft Teams correspondente. Conclua a ação para cada linha da seção Mapeamento de Campo. Para definições de cada campo ServiceNow, consulte [Definições de campo do ServiceNow](#servicenow-field-definitions).

| Campo ServiceNow | campo Salas do Microsoft Teams | Ação |
| --- | --- | --- |
| short_description | Descrição do incidente | Nenhuma ação necessária. O campo Salas do Teams é preenchido automaticamente. |
| Descrição | Primeira Mensagem | Nenhuma ação necessária. O campo Salas do Teams é preenchido automaticamente. |
| assignment_group | Grupo de salas | Copie o valor assignment_group na instância do ServiceNow e cole-o no campo valor ServiceNow no formulário de configuração. Se você tiver mais de uma assignment_group, selecione **Adicionar Grupo de Salas** para cada valor personalizado adicional. |
| Gravidade | Anéis | Severidade é um valor personalizado no ServiceNow. É o quarto item na segunda coluna da instância do ServiceNow. Copie o valor e cole-o no campo valor ServiceNow no formulário de configuração. Se você tiver mais de um valor de gravidade, selecione **Adicionar Anel** para cada valor personalizado adicional. |
| Comentários (opcional) | Valor personalizado* | Para adicionar um campo de comentários ao formulário de configuração, selecione **Adicionar** na parte superior da seção de mapeamento de campo. Copie o valor do comentário em sua instância do ServiceNow e cole-o no campo ServiceNow no formulário de configuração. Atribua-lhe um campo da Sala do Microsoft Teams no menu suspenso e copie e cole o valor ServiceNow. |
| estado (resolvido) | Valor personalizado* | Copie o estado de resolução da instância do ServiceNow e cole-o no campo valor ServiceNow no formulário de configuração. |
| close_code | Valor personalizado* | Na guia **Informações de Resolução** da instância do ServiceNow, copie o código de fechamento e cole-o no campo valor ServiceNow no formulário de configuração. |

*Selecione valores personalizados no menu suspenso

>[!NOTE]
>Se você não conseguir localizar seus valores personalizados, entre em contato com o administrador do ServiceNow.

Para adicionar campos necessários adicionais à seção Resolver Incidente, selecione **Adicionar**.

## <a name="test-and-enable"></a>Testar e habilitar

Depois de concluir o formulário de configuração, selecione **Testar** na parte inferior da página. O teste é necessário para enviar sua configuração.

Depois que o teste for aprovado com êxito, selecione **Enviar** para salvar suas alterações. Depois de estar pronto para habilitar o ServiceNow para sua organização, alterne o **ServiceNow?** 

## <a name="servicenow-field-definitions"></a>Definições de campo do ServiceNow

- **short_description**: o campo de descrição curta no ServiceNow é um valor alfanumérico breve de 160 caracteres que fornece um resumo do incidente. A descrição curta é equivalente à descrição de incidentes no portal de Gerenciamento de Salas Teams Pro.

- **descrição**: o campo de descrição no ServiceNow é o primeiro valor no histórico de conversas de um incidente do ServiceNow. A descrição é equivalente à primeira mensagem no portal de Gerenciamento de Salas Teams Pro.

- **assignment_group**: o campo grupo de atribuições no ServiceNow é usado para organizar incidentes. Os grupos de atribuição são equivalentes a grupos de salas no portal de Gerenciamento de Salas Teams Pro. Por padrão, há um grupo de quartos e mais podem ser adicionados. Você decide quantos grupos há e como agrupar seus incidentes. Por exemplo, você pode optar por organizar seus incidentes por local.

- **severidade**: o campo de gravidade no ServiceNow é usado para organizar incidentes por prioridade. Os valores que designam prioridade são personalizáveis. A gravidade é equivalente ao campo Ring no portal de Gerenciamento de Salas Teams Pro. Para personalizar anéis no portal de Gerenciamento de Salas Teams Pro, acesse **Atualizações** no menu de navegação esquerdo. Em seguida, vá para a guia **Anéis** e selecione **Adicionar anel**.

- comentários: Os comentários são um campo opcional no ServiceNow que é usado para incluir campos **obrigatórios** personalizados da instância do ServiceNow na configuração do portal de gerenciamento de Salas Teams Pro. O equivalente a comentários é um valor personalizado no portal de Gerenciamento de Salas Teams Pro.

- **estado (resolvido)**: o campo estado (resolvido) no ServiceNow é usado para designar como um incidente foi resolvido e é necessário fechar um incidente. O valor do estado (resolvido) é personalizável. O equivalente ao estado (resolvido) é um valor personalizado no portal de Gerenciamento de Salas Teams Pro.

- **close_code**: um código próximo deve ser atribuído a um incidente depois que ele for completamente resolvido. Esse valor é personalizável no ServiceNow. O equivalente ao código close é um valor personalizado no portal de Gerenciamento de Salas Teams Pro.
