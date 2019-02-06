---
title: Configurar a análise de chamada
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Configurar e usar a análise de chamada para identificar e resolver Skype para problemas de qualidade de chamada de negócios e Teams da Microsoft.
ms.openlocfilehash: 489dceae4924f3f720fd60f86423781c1aa31b41
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754547"
---
# <a name="set-up-call-analytics"></a>Configurar a análise de chamada

Como um equipes ou Skype do admin Business Online, você pode usar o Analytics chamadas para solucionar Skype para negócios e problemas de qualidade e conexão de chamada Teams da Microsoft. Você pode achar útil para configurar os seguintes recursos na análise de chamada:
  
- Definir permissões que permitem que outras pessoas, como operadores de assistência técnica, use a análise de chamada, mas impedir que eles acessem o restante do Centro de administração do Microsoft Teams. 
    
- Adicione informações de Inquilino, site e construção para análise chamada carregando um arquivo de dados. tsv ou. csv.
    
**Chamar Analytics agora está disponível no Centro de administração de equipes da Microsoft**. Para ver todas as informações de chamada e os dados de um usuário, use a guia de **Histórico de chamadas** . Você pode fazer isso observando na página de perfil do usuário, seguindo um destes procedimentos:

- Procure o usuário do painel.
  
   ![Captura de tela de pesquisa de usuário no painel](media/set-up-call-analytics-image-1.png)

-  Selecione os **usuários** no painel de navegação à esquerda.

   ![Captura de tela de navegação à esquerda](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a>Definir permissões de análise de chamada
<a name="BKMK_SetCAPerms"></a>

Como o administrador, você deve obter acesso total a todos os recursos de análise de chamada. Além disso, você pode atribuir funções do Azure Active Directory para a equipe de suporte. Atribua a função de especialista de suporte de comunicação de equipes a usuários que devem ter uma exibição limitada da análise de chamada. Atribua a função de engenheiro de suporte de comunicações equipes aos usuários que precisam acessar a funcionalidade completa do Analytics chamada. Ambos os níveis de permissão impedem o acesso ao restante do Centro de administração do Microsoft Teams.

> [!NOTE]
> A função de especialista de suporte de comunicações é equivalente ao suporte da camada 1 e a função de engenheiro de suporte de comunicações é equivalente ao suporte da camada 2.

Para obter mais informações sobre as funções de administrador de equipes, consulte [equipes da Microsoft que usar funções de administrador para gerenciar equipes](using-admin-roles.md). 
  
Especialistas de suporte de comunicações lidar com problemas de qualidade de chamada básicos. Eles não investigar problemas com reuniões. Em vez disso, eles coletam informações relacionadas e, em seguida, escalonar para um engenheiro de suporte de comunicações. Engenheiros de suporte de comunicações consulte informações nos logs de chamada detalhadas ocultas de comunicações de especialistas de suporte. A tabela a seguir oferece uma visão geral das informações disponíveis aos engenheiros de suporte a comunicações suporte communications e especialistas quando utilizarem a análise de chamada.

|**Atividade**|**Informações na análise de chamada**|**As comunicações que oferecem suporte a vê especialista em**|**Quais as comunicações vê engenheiro de suporte**|
|:-----|:-----|:-----|:-----|
|**Chamadas** <br/> |Nome do chamador  <br/> |Somente o nome do usuário para o qual o agente pesquisadas.  <br/> |Nome de usuário.  <br/> |
||Nome do destinatário  <br/> |Mostra como usuário interno ou externo do usuário.  <br/> |Nome do destinatário.  <br/> |
||Número de telefone do chamador  <br/> |Número de telefone inteira, exceto os últimos três dígitos são ofuscados por símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |Número de telefone inteira, exceto os últimos três dígitos são ofuscados por símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |
||Número de telefone do destinatário  <br/> |Número de telefone inteira, exceto os últimos três dígitos são ofuscados por símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |Número de telefone inteira, exceto os últimos três dígitos são ofuscados por símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |
||**Detalhes da chamada** > guia**Avançado** <br/> |Informações não mostradas.  <br/> |Todos os detalhes mostrados, como nomes de dispositivo, endereço IP, mapeamento de sub-rede e muito mais.  <br/> |
||**Detalhes da chamada** > **Avançado** > guia**Debug** <br/> |Informações não mostradas.  <br/> |Todos os detalhes mostrados, como o sufixo DNS e SSID.  <br/> |
|**Reuniões** <br/> |Nomes dos participantes  <br/> |Somente o nome do usuário para o qual o agente pesquisadas. Outros participantes identificados como usuário interno ou externo do usuário.  <br/> |Todos os nomes mostrados.  <br/> |
||Contagem de participantes  <br/> |Número de participantes.  <br/> |Número de participantes.  <br/> |
||Detalhes da sessão  <br/> |Detalhes da sessão mostradas com exceções. Somente o nome do usuário para o qual o agente pesquisadas é mostrado. Outros participantes identificados como usuário interno ou externo do usuário. Últimos três dígitos do número de telefone ofuscados por símbolos de asterisco.  <br/> |Detalhes da sessão mostrados. Nomes de usuário e os detalhes de sessão mostrados. Últimos três dígitos do número de telefone ofuscados por símbolos de asterisco.  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a>Configurar as permissões, atribuindo funções de administrador
<a name="BKMK_SetUpTier"> </a>

Para saber como atribuir funções administrativas no Windows Azure Active Directory, consulte [Exibir e atribuir funções no Windows Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Carregar um arquivo. tsv ou. csv para adicionar a criação de site e informações de locatários
<a name="BKMK_UploadFiles"> </a>

Você pode adicionar construção, sites e informações de Inquilino para chamar Analytics carregando um arquivo. csv ou. tsv. Com essa informação, chamada Analytics pode mapear endereços IP para locais físicos. Você ou da assistência técnica agentes podem encontrar essas informações úteis para ajudar a identificar tendências em problemas de chamada. Por exemplo, por que são muitos usuários no mesmo prédio tendo semelhantes chama problemas de qualidade? 

Se você for um equipes e Skype para administração de negócios, você pode usar um arquivo de dados existente do & equipes Skype para painel de qualidade de chamada de negócios. Primeiro, você baixe o arquivo do painel de controle de qualidade de chamada e, em seguida, você o carrega no Analytics chamada. 

- Para baixar um arquivo de dados existente, vá para **o Centro de administração do Microsoft equipes** > **Painel de qualidade de chamada** > **Carregar Agora**. Na lista **Meus carregamentos** , clique em **Baixar** ao lado do arquivo que você deseja.

- Para carregar o novo arquivo, vá para **o Centro de administração do Microsoft equipes** > **locais**e selecione **carregar dados do local** ou **substituir dados de local**.
  
Se você estiver criando o arquivo. csv ou. tsv desde o início, consulte o [formato e a estrutura do arquivo de dados de criação do arquivo de dados de Inquilino](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Tópicos relacionados
<a name="BKMK_UploadFiles"> </a>

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade das chamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de chamada e o painel de controle de qualidade de chamada](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
