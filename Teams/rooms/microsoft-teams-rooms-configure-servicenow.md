---
title: Configurar ServiceNow para Salas do Teams
author: cazawideh
ms.author: czawideh
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Saiba mais sobre como configurar ServiceNow no portal Salas do Teams Premium portal
f1keywords: ''
ms.openlocfilehash: deca4f8111dec958b19d9a6fa2651fca34f4050f
ms.sourcegitcommit: 9caa3131e9896b140afe10edea2b1e599eacd02b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/19/2022
ms.locfileid: "62082207"
---
# <a name="configure-servicenow-for-teams-rooms"></a>Configurar ServiceNow para Salas do Teams

Este artigo descreve os pré-requisitos e as etapas para configurar seu ambiente ServiceNow no portal Salas do Teams Premium.

## <a name="before-you-begin"></a>Antes de você começar

### <a name="teams-rooms-prerequisites"></a>Salas do Teams pré-requisitos

- Você deve ter uma função de Administrador de Serviço atribuída. Para obter mais informações, consulte [Role-based access control with the Salas do Microsoft Teams Managed Services](microsoft-teams-rooms-premium-rbac.md).

### <a name="servicenow-prerequisites"></a>Pré-requisitos serviceNow

- Uma assinatura autorização básica ou uma assinatura [OAuth.](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) Para obter mais informações, consulte [Creating Credentials](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) in ServiceNow.
- Uma instância serviceNow e seu nome de host de instância e URI de API
- Uma função de incident_manager ou superior
- Uma versão de software do ServiceNow que oferece suporte à API de tabela

## <a name="configure-your-environment"></a>Configurar seu ambiente

A configuração do seu ambiente é altamente personalizável e dependerá das necessidades da sua organização. As etapas a seguir mostram como copiar a configuração existente no ServiceNow para o portal Salas do Teams Premium.

1. Abra a instância ServiceNow que você deseja copiar. Você precisará fazer referência a isso ao concluir o formulário de configuração no Salas do Teams Premium portal.
2. Em uma nova guia do navegador, vá para o [portal Salas do Teams Premium e](https://portal.rooms.microsoft.com/) vá para **Configurações**. Em seguida, selecione **ServiceNow** no menu de navegação esquerdo para abrir o formulário de configuração.
3. Selecione um método de autenticação para entrar e inserir seu Host de Instância serviceNow e URI de API.
4. Todos os itens necessários na coluna Campo ServiceNow da seção Mapeamento de Campos devem ser preenchidos previamente. A tabela abaixo contém cada campo ServiceNow e seu campo Salas do Microsoft Teams correspondente. Conclua a ação para cada linha da seção Mapeamento de Campos. Para definições de cada campo ServiceNow, consulte [ServiceNow field definitions](#servicenow-field-definitions).

| Campo ServiceNow | Salas do Microsoft Teams campo | Ação |
| --- | --- | --- |
| short_description | Descrição do incidente | Nenhuma ação necessária. O Salas do Teams campo é preenchido automaticamente. |
| description | Primeira Mensagem | Nenhuma ação necessária. O Salas do Teams campo é preenchido automaticamente. |
| assignment_group | Grupo de sala | Copie o assignment_group valor em sua instância serviceNow e o colar no campo valor ServiceNow no formulário de configuração. Se você tiver mais de um assignment_group, selecione **Adicionar Grupo** de Sala para cada valor personalizado adicional. |
| severidade | Rings | Severidade é um valor personalizado em ServiceNow. É o quarto item na segunda coluna da sua instância ServiceNow. Copie o valor e o colar no campo valor ServiceNow no formulário de configuração. Se você tiver mais de um valor de gravidade, selecione **Adicionar Anel** para cada valor personalizado adicional. |
| Comentários (opcional) | Valor personalizado* | Para adicionar um campo de comentários ao formulário de configuração, selecione **Adicionar** na parte superior da seção mapeamento de campo. Copie o valor do comentário em sua instância ServiceNow e o colar no campo ServiceNow no formulário de configuração. Atribua a ele Microsoft Teams campo Sala do menu suspenso e copie e colar o valor ServiceNow. |
| state (resolvido) | Valor personalizado* | Copie o estado de resolução da sua instância ServiceNow e o colar no campo valor ServiceNow no formulário de configuração. |
| close_code | Valor personalizado* | Na guia **Informações de Resolução** da sua instância serviceNow, copie o código de fechamento e o colar no campo valor ServiceNow no formulário de configuração. |

*Selecione valores personalizados no menu suspenso

>[!NOTE]
>Se você não conseguir localizar seus valores personalizados, entre em contato com o administrador do ServiceNow.

Para adicionar campos adicionais necessários à seção Resolver Incidentes, selecione **Adicionar**.

## <a name="test-and-enable"></a>Testar e habilitar

Depois de concluir o formulário de configuração, selecione **Testar** na parte inferior da página. Os testes são necessários para enviar sua configuração.

Depois que o teste for aprovado com êxito, selecione **Enviar** para salvar suas alterações. Quando estiver pronto para habilitar ServiceNow para sua organização, alterne o botão Deseja habilitar **ServiceNow?** alternar para **Ativado.**

## <a name="servicenow-field-definitions"></a>Definições de campo ServiceNow

- **short_description**: o campo de descrição curta em ServiceNow é um valor alfanumérico breve de 160 caracteres que fornece um resumo do incidente. A descrição curta equivale à descrição do incidente no portal Salas do Teams Premium.

- **description**: O campo de descrição em ServiceNow é o primeiro valor no histórico de conversas de um incidente ServiceNow. Descrição é equivalente à Primeira mensagem no portal Salas do Teams Premium.

- **assignment_group:** o campo de grupo de atribuição em ServiceNow é usado para organizar incidentes. O grupo de atribuições é equivalente aos grupos de sala no portal Salas do Teams Premium. Por padrão, há um grupo de sala e mais podem ser adicionados. Você decide quantos grupos há e como agrupar seus incidentes. Por exemplo, você pode optar por organizar seus incidentes por local.

- **severidade**: O campo de severidade em ServiceNow é usado para organizar incidentes por prioridade. Os valores que designam prioridade são personalizáveis. A gravidade é equivalente ao campo Anel no portal Salas do Teams Premium. Para personalizar anéis no portal Salas do Teams Premium, vá para **Atualizações** no menu de navegação à esquerda. Em seguida, vá para a guia **Anéis** e selecione **Adicionar anel**.

- **comentários**: Os comentários são um campo opcional em ServiceNow que é usado para incluir campos necessários personalizados da sua instância serviceNow na configuração Salas do Teams Premium portal. O equivalente a comentários é um valor personalizado no Salas do Teams Premium portal.

- **estado (resolvido)**: o campo estado (resolvido) em ServiceNow é usado para designar como um incidente foi resolvido e é necessário para fechar um incidente. O valor de estado (resolvido) é personalizável. O equivalente ao estado (resolvido) é um valor personalizado no portal Salas do Teams Premium.

- **close_code:** um código de fechamento deve ser atribuído a um incidente quando ele for completamente resolvido. Esse valor é personalizável em ServiceNow. O equivalente ao código de fechamento é um valor personalizado no portal Salas do Teams Premium portal.
