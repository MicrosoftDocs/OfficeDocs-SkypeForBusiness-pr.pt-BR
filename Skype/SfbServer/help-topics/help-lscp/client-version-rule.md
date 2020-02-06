---
title: Regra de Versão do Cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Uma política de versão de cliente é composta por um conjunto de regras de versão de cliente. Essas regras definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes específicos e versões do cliente.
ms.openlocfilehash: 870f0d46ff50b4fabab9b4f098cb569ae2c9ee82
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823054"
---
# <a name="client-version-rule"></a>Regra de Versão do Cliente

Uma política de versão de cliente é composta por um conjunto de regras de versão de cliente. Essas regras definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes específicos e versões do cliente.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Criar uma nova Configuração de Versão de Cliente** ou **Editar Configuração da Versão de Cliente**:

- Adicionar novas regras a uma política de versão de cliente.

- Modificar as regras que compõem uma política de versão de cliente existente

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comando, campos e propriedades na página.

- **Agente de usuário** Você pode selecionar um tipo de cliente na lista. A tabela a seguir define códigos de agente de usuário.

|**Nome do cliente**|**Agente de Usuário**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Access Web Communicator  <br/> |CWA  <br/> |
|Lync Phone Edition, Office Communicator Phone  <br/> |OCPhone  <br/> |
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

- **Número da versão** Você pode especificar os números de versão para os campos a seguir ou usar caracteres curinga para indicar o número da versão do cliente.

  - **Versão principal** Especifica o número que corresponde à versão principal do cliente.

  - **Versão secundária** Especifica o número que corresponde à versão secundária do cliente.

  - **Criar** Especifica o número da compilação que corresponde à versão principal e secundária do cliente.

  - **Atualização** do Especifica o número que corresponde à versão atualizada do cliente.

- **Operação de comparação** Você pode especificar a operação correspondente para a versão do cliente que você especificou nas etapas anteriores. As operações a seguir estão disponíveis:

  - **Igual a**

  - **Não é**

  - **Mais novo que**

  - **Mais novo ou igual a**

  - **Mais antigo que**

  - **Mais antigo ou igual a**

- **Ação** Você pode especificar a ação a ser executada quando os critérios nas etapas anteriores forem atendidos. As ações a seguir estão disponíveis:

  - **Permite que** Permite que o cliente faça logon.

  - **Permitir e atualizar** Permite que o cliente faça logon e Receba atualizações do Windows Server Update Service ou do Microsoft Update. Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.

    > [!NOTE]
    > Selecionar essa ação faz com que uma notificação seja exibida na próxima vez que os usuários entrarem no Skype for Business. A notificação declara que uma atualização está disponível, mesmo se as atualizações ainda não tiverem sido lançadas pelo Windows Server Update Service ou Microsoft Update. Para evitar confusão, você deve escolher esta ação apenas após as atualizações se tornarem disponíveis.

  - **Permitir com URL** Permite que o cliente faça logon e exiba uma mensagem sobre onde baixar outra versão do cliente. Especifique o URL no campo  **URL**.

  - **Bloquear** Impede que o cliente faça logon.

  - **Bloquear e atualizar** Impede que o cliente faça logon e permite que o cliente Receba atualizações do Windows Server Update Service ou do Microsoft Update. Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.

  - **Bloquear com URL** Impede que o cliente faça logon e exibe uma mensagem sobre onde baixar outra versão do cliente. Especifique o URL no campo  **URL**.

Para obter detalhes sobre a interoperabilidade entre clientes e versões de clientes, consulte [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) na documentação Planejamento. Para obter detalhes sobre como trabalhar com configurações de versão de cliente, consulte [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) na documentação Operações.

