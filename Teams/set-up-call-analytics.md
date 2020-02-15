---
title: Configurar Análise de Chamada
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configurar e usar a análise de chamadas para identificar e solucionar problemas de qualidade de chamada do Skype for Business e do Microsoft Teams.
ms.openlocfilehash: 347725e77806f94e44b4c8d160736ceb23265f11
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029402"
---
# <a name="set-up-call-analytics"></a>Configurar Análise de Chamada

Como um administrador do teams ou do Skype for Business Online, você pode usar a análise de chamadas para solucionar problemas de qualidade e conexão de chamadas do Skype for Business e do Microsoft Teams. Pode ser útil configurar os recursos a seguir na análise de chamadas:
  
- Defina permissões que permitam a outros funcionários, como agentes de assistência técnica, usar o recurso de análise de chamadas, mas evitar que eles acessem o restante do centro de administração do Microsoft Teams. 
    
- Adicione informações de construção, site e locatário para fazer uma chamada de análise ao carregar um arquivo de dados. tsv ou. csv.
    
**O recurso de análise de chamadas agora está disponível no centro de administração do Microsoft Teams**. Para ver todas as informações de chamada e dados de um usuário, use a guia **histórico de chamadas** . Você pode fazer isso consultando a página de perfil do usuário seguindo um destes procedimentos:

- Procure pelo usuário no painel.
  
   ![Captura de tela da pesquisa do usuário no painel](media/set-up-call-analytics-image-1.png)

-  Selecione **usuários** na navegação à esquerda.

   ![Captura de tela da navegação à esquerda](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a>Definir permissões para a análise de chamadas
<a name="BKMK_SetCAPerms"></a>

Como administrador, você tem acesso total a todos os recursos do recurso de análise de chamadas. Além disso, você pode atribuir funções do Azure Active Directory a equipe de suporte. Atribua a função de especialista de comunicações do teams a usuários que devem ter uma visão limitada da análise de chamadas. Atribua a função de engenheiro de suporte de comunicações ao Teams a usuários que precisam acessar a funcionalidade completa do recurso de análise de chamadas. Os dois níveis de permissão impedem o acesso ao restante do centro de administração do Microsoft Teams.

> [!NOTE]
> A função de especialista de suporte de comunicações é equivalente ao suporte de nível 1 e a função de engenheiro de suporte de comunicações equivale ao suporte de nível 2.

Para obter mais informações sobre as funções de administração do Teams, consulte [usar funções de administrador do Microsoft Teams para gerenciar o Teams](using-admin-roles.md). 
  
Especialistas de suporte de comunicações lidam com problemas básicos de qualidade de chamada. Eles não investigam problemas com reuniões. Em vez disso, eles coletam informações relacionadas e encaminham para um engenheiro de suporte de comunicações. Engenheiros de suporte a comunicações consulte informações em logs de chamadas detalhados que estão ocultos a especialistas de suporte de comunicações. A tabela a seguir fornece uma visão geral das informações disponíveis para especialistas de suporte de comunicações e engenheiros de suporte de comunicações quando eles usam a análise de chamadas.

|**Atividades**|**Informações na análise de chamadas**|**O que o especialista de suporte de comunicações vê**|**O que o engenheiro de suporte a comunicações vê**|
|:-----|:-----|:-----|:-----|
|**Chamadas** <br/> |Nome do chamador  <br/> |Somente o nome do usuário para o qual o agente procurou.  <br/> |Nome de usuário.  <br/> |
||Nome do destinatário  <br/> |Mostra como usuário interno ou externo.  <br/> |Nome do destinatário.  <br/> |
||Número de telefone do chamador  <br/> |Número de telefone inteiro, exceto os últimos três dígitos, ofuscados com símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |Número de telefone inteiro, exceto os últimos três dígitos, ofuscados com símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |
||Número de telefone do destinatário  <br/> |Número de telefone inteiro, exceto os últimos três dígitos, ofuscados com símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |Número de telefone inteiro, exceto os últimos três dígitos, ofuscados com símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |
||**** > Guia**avançado** de detalhes da chamada <br/> |As informações não são mostradas.  <br/> |Todos os detalhes mostrados, como nomes de dispositivos, endereços IP, mapeamento de sub-rede e muito mais.  <br/> |
||**** > Guia**depuração** **avançada** > de detalhes da chamada <br/> |As informações não são mostradas.  <br/> |Todos os detalhes exibidos, como sufixo DNS e SSID.  <br/> |
|**Reuniões** <br/> |Nomes dos participantes  <br/> |Somente o nome do usuário para o qual o agente procurou. Outros participantes identificados como usuário interno ou usuário externo.  <br/> |Todos os nomes mostrados.  <br/> |
||Contagem de participantes  <br/> |Número de participantes.  <br/> |Número de participantes.  <br/> |
||Detalhes da sessão  <br/> |Detalhes da sessão mostrados com exceções. Somente o nome do usuário para o qual o agente procurou é mostrado. Outros participantes identificados como usuário interno ou usuário externo. Os últimos três dígitos do número de telefone ofuscados com símbolos de asterisco.  <br/> |Detalhes da sessão mostrados. Nomes de usuário e detalhes da sessão mostrados. Os últimos três dígitos do número de telefone ofuscados com símbolos de asterisco.  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a>Configurar permissões atribuindo funções de administrador
<a name="BKMK_SetUpTier"> </a>

Para saber como atribuir funções administrativas no Azure Active Directory, consulte [Exibir e atribuir funções no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Carregar um arquivo. tsv ou. csv para adicionar informações de criação, site e locatário
<a name="BKMK_UploadFiles"> </a>

Você pode adicionar informações de construção, site e locatário para fazer uma chamada de análise para fazer o upload de um arquivo. csv ou. TSV. Com todas essas informações, a análise de chamadas pode mapear endereços IP para locais físicos. Os agentes da assistência técnica ou da assistência técnica podem encontrar essas informações úteis para ajudar a identificar tendências em problemas com chamadas. Por exemplo, por que muitos usuários na mesma criação têm problemas de qualidade de chamada semelhantes? 

Se você é um administrador do Teams e do Skype for Business, pode usar um arquivo de dados existente do teams & painel de qualidade de chamada do Skype for Business. Primeiro, baixe o arquivo do painel de qualidade de chamada e, em seguida, carregue-o para a análise de chamadas. 

- Para baixar um arquivo de dados existente, acesse o > **painel** > de qualidade de chamada **do centro de administração do Microsoft Teams****agora**. Na lista **meus uploads** , clique em **baixar** ao lado do arquivo desejado.

- Para carregar o novo arquivo, vá para > **locais**do **centro de administração do Microsoft Teams**e, em seguida, selecione **carregar dados de localização** ou **substituir dados de localização**.
  
Se você estiver criando o arquivo. tsv ou. csv do zero, consulte [formato de arquivo de dados locatários e estrutura de arquivo de dados de construção](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Tópicos relacionados
<a name="BKMK_UploadFiles"> </a>

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de Chamada e Painel de Qualidade de Chamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
