---
title: Regra de Versão do Cliente
ms.author: dianef
author: dianef77
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: Uma política de versão de cliente é composta por um conjunto de regras de versão de cliente. Essas regras definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes específicos e versões do cliente.
ms.openlocfilehash: cd89e0bd5bf6781ea8381563e592d57a3e68434a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988731"
---
# <a name="client-version-rule"></a>Regra de Versão do Cliente
 
Uma política de versão de cliente é composta por um conjunto de regras de versão de cliente. Essas regras definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes específicos e versões do cliente.
  
## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Criar uma nova Configuração de Versão de Cliente** ou **Editar Configuração da Versão de Cliente**:
  
- Adicionar novas regras a uma política de versão de cliente.
    
- Modificar as regras que compõem uma política de versão de cliente existente
    
## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comando, campos e propriedades na página.
  
- **Agente do usuário** Você pode selecionar um tipo de cliente da lista. A tabela a seguir define códigos de agente de usuário.
    
|**Nome do cliente**|**Agente do usuário**|
|:-----|:-----|
|Lync 2013, Lync 2010, o Office Communicator  <br/> |OC  <br/> |
|Lync Web App, o Communicator Web Access  <br/> |CWA  <br/> |
|O Lync Phone Edition, o Office Communicator Phone  <br/> |OCPhone  <br/> |
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
   
- **Número de versão** Você pode especificar os números de versão para os seguintes campos ou usar caracteres curinga para indicar o número de versão do cliente.
    
  - **Versão principal** Especifica o número que corresponde à principal versão do cliente.
    
  - **Versão secundária** Especifica o número que corresponde à versão secundária do cliente.
    
  - **Construir** Especifica o número de compilação que corresponde à versão principal e secundária do cliente.
    
  - **Atualização** Especifica o número que corresponde à versão atualizada do cliente.
    
- **Operação de comparação** Você pode especificar a operação correspondente para a versão de cliente especificada nas etapas anteriores. As operações a seguir estão disponíveis:
    
  - **Igual a**
    
  - **Não é**
    
  - **Mais novo que**
    
  - **Mais novo ou igual a**
    
  - **Mais antigo que**
    
  - **Mais antigo ou igual a**
    
- **Ação** Você pode especificar a ação a ser executada quando os critérios nas etapas anteriores forem atendidos. As ações a seguir estão disponíveis:
    
  - **Permitir** Permite que o cliente faça logon.
    
  - **Permitir e atualizar** Permite que o cliente faça logon e receber atualizações de serviço de atualização do Windows Server ou o Microsoft Update. Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.
    
    > [!NOTE]
    > Selecionar esta ação faz com que uma notificação apareça os próxima vez que os usuários entram no Skype para negócios. A notificação declara que uma atualização está disponível, mesmo se as atualizações ainda não tiverem sido lançadas pelo Windows Server Update Service ou Microsoft Update. Para evitar confusão, você deve escolher esta ação apenas após as atualizações se tornarem disponíveis. 
  
  - **Permitir com URL** Permite que o cliente faça logon e exibe uma mensagem sobre onde baixar outra versão do cliente. Especifique o URL no campo  **URL**.
    
  - **Bloquear** Impede o cliente de logon.
    
  - **Bloquear e atualização** Impede que o cliente logon e permite que o cliente recebe atualizações do serviço de atualização do Windows Server ou Microsoft Update. Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.
    
  - **Bloquear com URL** Impede que o cliente faça logon e exibe uma mensagem sobre onde baixar outra versão do cliente. Especifique o URL no campo  **URL**.
    
Para obter detalhes sobre a interoperabilidade entre clientes e versões de cliente, consulte [Client Interoperability](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) na documentação de planejamento. Para obter detalhes sobre como trabalhar com as configurações de versão de cliente, consulte [modificar a ação padrão para clientes não explicitamente suportados ou restritos](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) na documentação operações.

