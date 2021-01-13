---
title: Regra de Versão de Cliente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: Uma política de versão de cliente é composta por um conjunto de regras de versão de cliente. Essas regras definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes específicos e versões do cliente.
ms.openlocfilehash: 26f37c77886ac9f9fe7fb8d8680fb0dad642a9cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812371"
---
# <a name="client-version-rule"></a>Regra da Versão de Cliente

Uma política de versão de cliente é composta por um conjunto de regras de versão de cliente. Essas regras definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes específicos e versões do cliente.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Criar uma nova Configuração de Versão de Cliente** ou **Editar Configuração da Versão de Cliente**:

- Adicionar novas regras a uma política de versão de cliente.

- Modificar as regras que compõem uma política de versão de cliente existente

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comando, campos e propriedades na página.

- **Agente do usuário** Você pode selecionar um tipo de cliente na lista. A tabela a seguir define códigos de agente de usuário. Essa lista inclui tipos de cliente herdados, alguns dos quais não são mais suportados.

|**Nome do cliente**|**Agente do Usuário**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
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

- **Número da versão** Você pode especificar os números de versão para os campos a seguir ou usar caracteres curinga para indicar o número de versão do cliente.

  - **Versão principal** Especifica o número que corresponde à versão principal do cliente.

  - **Versão secundária** Especifica o número que corresponde à versão secundária do cliente.

  - **Build** Especifica o número de com build que corresponde à versão principal e secundária do cliente.

  - **Atualizar** Especifica o número que corresponde à versão atualizada do cliente.

- **Operação de comparação** Você pode especificar a operação correspondente para a versão do cliente especificada nas etapas anteriores. As operações a seguir estão disponíveis:

  - **igual a**

  - **Não é**

  - **Mais novo que**

  - **Mais novo ou igual a**

  - **Mais antigo que**

  - **Mais antigo ou igual a**

- **Ação** Você pode especificar a ação a ser tomada quando os critérios nas etapas anteriores são atendidos. As ações a seguir estão disponíveis:

  - **Permitir** Permite que o cliente faça logoff.

  - **Permitir e Atualizar** Permite que o cliente faça logoff e receba atualizações do Windows Server Update Service ou do Microsoft Update. Esta ação está disponível apenas quando o agente do usuário **OC** é selecionado.

    > [!NOTE]
    > Selecionar essa ação faz com que uma notificação apareça na próxima vez que os usuários entrarem no Skype for Business. A notificação declara que uma atualização está disponível, mesmo se as atualizações ainda não tiverem sido lançadas pelo Windows Server Update Service ou Microsoft Update. Para evitar confusão, você deve escolher esta ação apenas após as atualizações se tornarem disponíveis.

  - **Permitir com URL** Permite que o cliente faça logoff e exibe uma mensagem sobre onde baixar outra versão do cliente. Especifique o URL no campo **URL**.

  - **Bloquear** Impede o cliente de fazer logon.

  - **Bloquear e atualizar** Impede o cliente de fazer logon e permite que o cliente receba atualizações do Windows Server Update Service ou do Microsoft Update. Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.

  - **Bloquear com URL** Impede que o cliente faça logon e exibe uma mensagem sobre onde baixar outra versão do cliente. Especifique o URL no campo **URL**.

Para obter detalhes sobre interoperabilidade entre clientes e versões de cliente, consulte [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. Para obter detalhes sobre como trabalhar com configurações de versão de cliente, consulte [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) na documentação Operações.

