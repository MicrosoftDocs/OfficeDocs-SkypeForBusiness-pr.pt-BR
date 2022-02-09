---
title: Regra de Versão de Cliente
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Uma política de versão de cliente é composta por um conjunto de regras de versão de cliente. Essas regras definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes específicos e versões do cliente.
ms.openlocfilehash: 3a2aa4712fdbe6d4c59a8ce72c67c2603f00cf57
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404103"
---
# <a name="client-version-rule"></a>Regra da Versão de Cliente

Uma política de versão de cliente é composta por um conjunto de regras de versão de cliente. Essas regras definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes específicos e versões do cliente.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Criar uma nova Configuração de Versão de Cliente** ou **Editar Configuração da Versão de Cliente**:

- Adicionar novas regras a uma política de versão de cliente.

- Modificar as regras que compõem uma política de versão de cliente existente

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comando, campos e propriedades na página.

- **Agente de usuário** Você pode selecionar um tipo de cliente na lista. A tabela a seguir define códigos de agente de usuário.

|**Nome do cliente**|**Agente do Usuário**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Lync Telefone Edition, Office Communicator Telefone  <br/> |OCPhone  <br/> |
|Communicator Phone Edition Platform  <br/> |CPE  <br/> |
|Unified Communications Platform  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |AOC  <br/> |
|Live Meeting Add-In  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|Real-time Communications Client  <br/> |RTC  <br/> |
|Lync 2010 para iPad  <br/> |iPadLync  <br/> |
|Lync 2010 para iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 para Windows Phone  <br/> |WPLync  <br/> |
|Lync 2010 para Nokia  <br/> |NokiaLync  <br/> |
|Lync 2010 para Android  <br/> |AndroidLync  <br/> |
|Serviço de mobilidade  <br/> |McxService  <br/> |

- **Número da versão** Você pode especificar os números de versão para os campos a seguir ou usar curingas para indicar o número da versão do cliente.

  - **Versão principal** Especifica o número que corresponde à versão principal do cliente.

  - **Versão secundária** Especifica o número que corresponde à versão secundária do cliente.

  - **Build** Especifica o número de com build que corresponde à versão principal e secundária do cliente.

  - **Atualização** Especifica o número que corresponde à versão atualizada do cliente.

- **Operação de comparação** Você pode especificar a operação correspondente para a versão do cliente especificada nas etapas anteriores. As operações a seguir estão disponíveis:

  - **igual a**

  - **Não é**

  - **Mais novo que**

  - **Mais novo ou igual a**

  - **Mais antigo que**

  - **Mais antigo ou igual a**

- **Ação** Você pode especificar a ação a ser cumprida quando os critérios nas etapas anteriores são atendidos. As ações a seguir estão disponíveis:

  - **Permitir** Permite que o cliente faça logoff.

  - **Permitir e atualizar** Permite que o cliente faça logoff e receba atualizações Windows Server Update Service ou Microsoft Update. Esta ação está disponível apenas quando o agente do usuário **OC** é selecionado.

    > [!NOTE]
    > Selecionar essa ação faz com que uma notificação apareça na próxima vez que os usuários entrarem Skype for Business. A notificação declara que uma atualização está disponível, mesmo se as atualizações ainda não tiverem sido lançadas pelo Windows Server Update Service ou Microsoft Update. Para evitar confusão, você deve escolher esta ação apenas após as atualizações se tornarem disponíveis.

  - **Permitir com URL** Permite que o cliente faça logoff e exibe uma mensagem sobre onde baixar outra versão do cliente. Especifique o URL no campo **URL**.

  - **Bloquear** Impede que o cliente entre em log.

  - **Bloquear e atualizar** Impede o cliente de fazer logon e permite que o cliente receba atualizações do serviço de atualização do Windows Server Update ou do Microsoft Update. Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.

  - **Bloquear com URL** Impede que o cliente faça logon e exibe uma mensagem sobre onde baixar outra versão do cliente. Especifique o URL no campo **URL**.

Para obter detalhes sobre a interoperabilidade entre clientes e versões de clientes, consulte [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) na documentação Planejamento. Para obter detalhes sobre como trabalhar com configurações de versão de cliente, consulte [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) na documentação Operações.