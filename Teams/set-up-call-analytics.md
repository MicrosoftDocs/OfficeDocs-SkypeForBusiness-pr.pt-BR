---
title: Configurar a análise de chamada
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Configurar e usar a análise de chamada para identificar e resolver Skype para problemas de qualidade de chamada de negócios e Teams da Microsoft.
ms.openlocfilehash: d2e4a603010f668fa0b9a2767b1580d4b9b71a47
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23784874"
---
# <a name="set-up-call-analytics"></a>Configurar a análise de chamada

Como um Skype do admin Business Online, você pode usar o Analytics chamada solucionar Skype for Business e Microsoft Teams problemas de qualidade e conexão de chamada. Você pode achar útil para configurar os seguintes recursos na análise de chamada:
  
- Definir permissões que permitem que outras pessoas, como operadores de assistência técnica, use a análise de chamada, mas impedir que eles acessem o restante do Skype para centro de administração de negócios. 
    
- Adicione informações de Inquilino, site e construção para análise chamada carregando um arquivo de dados. tsv ou. csv.
    
**Análise de chamada agora está disponível no Microsoft Teams e Skype para Business Admin Center.** Para ver todas as informações de chamada e os dados de um usuário, use a guia de **Histórico de chamadas** . Você pode fazer isso por procurando na página de perfil do usuário, qualquer procurando por usuário do painel ou localizar o usuário dos **usuários** no painel de navegação à esquerda.

> [!IMPORTANT]
> Permissões de operador de assistência técnica e carregamento de topologia de rede estará disponíveis no portal de administração do novo nos próximos meses. Enquanto isso, você pode continuar a usar https://adminportal.services.skypeforbusiness.com para acesso de assistência técnica de camada 1 e a camada 2.
  
## <a name="set-call-analytics-permissions"></a>Definir permissões de análise de chamada
<a name="BKMK_SetCAPerms"></a>

Como o administrador, você deve obter acesso total a todos os recursos de análise de chamada. Além disso, você pode usar um modelo de assistência técnica na análise de chamada que inclui os grupos de permissões de nível 1 e 2 de camada. Usuários com permissões de nível 1 podem acessar apenas um modo de exibição limitado de análise de chamada. Usuários com permissões de nível 2 podem acessar a funcionalidade completa do Analytics chamada. Ambos os níveis de permissão impedem o acesso ao restante do Microsoft Teams e Skype para Business Admin Center. Você pode conceder acesso às camadas, adicionando um grupo que contém o usuário a camada 1 ou a seção de nível 2 da página permissões. Para obter detalhes, consulte [Configure permissões hierárquicos na análise de chamada](set-up-call-analytics.md#BKMK_SetUpTier).
  
Operadores de assistência técnica da camada 1 lidar com problemas de qualidade de chamada básicos. Os agentes de nível 1 não investigar problemas com reuniões; eles coletam informações relacionadas e, em seguida, escalonar para um agente de nível 2. Os agentes de nível 2 ver a informação é oculto da camada 1 agentes nos logs de chamada detalhadas. A tabela a seguir oferece uma visão geral das informações disponíveis para os operadores por meio de análises de chamada.


|**Atividade**|**Informações na análise de chamada**|**O que vê o agente de nível 1**|**O que vê o agente de nível 2**|
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
   
 **Configurar as permissões hierárquicos na análise de chamada** 
 <a name="BKMK_SetUpTier"> </a>

![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**
  
1. Criar grupos de segurança do Office 365 para camada 1 e 2 de camada e adicione as pessoas que deseja a cada grupo. Você também pode reutilizar os grupos de segurança existentes. Para obter mais informações, consulte [Criar, editar ou excluir um grupo de segurança no centro de administração do Office 365](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).
    
2. No Centro de administração do Office 365, vá até **Admin centrais** > **Skype para negócios**.

    > [!NOTE]
    > Se você estiver nas **equipes da Microsoft e Skype para Business Admin Center**, no painel de navegação esquerdo, clique em **portal herdada**.
  
3. Na **Análise de chamada (preview)**, clique em **permissões**.
    
4. Adicione os grupos de segurança do Office 365 para as caixas de **nível 1** e **2 de camada** . Você pode adicionar vários grupos a cada função.
    
     ![Captura de tela mostra a página permissões para análise de chamada com as opções para permissões de nível 1 e 2 de camada.](media/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
 Usuários com qualquer um desses níveis de permissão chegar ao chamar Analytics por meio da URL dedicada *https://adminportal.services.skypeforbusiness.com*.
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Carregar um arquivo. tsv ou. csv para adicionar a criação de site e informações de locatários
<a name="BKMK_UploadFiles"> </a>

Você pode adicionar construção, sites e informações de Inquilino para chamar Analytics carregando um arquivo. csv ou. tsv. Com essa informação, chamada Analytics pode mapear endereços IP para locais físicos. Você ou da assistência técnica agentes podem encontrar essas informações úteis para ajudar a identificar tendências em problemas de chamada. Por exemplo, por que são muitos usuários no mesmo prédio tendo semelhantes chama problemas de qualidade? 
  
![Captura de tela mostra a página de Sites com valores para o número de sites e o número de sub-redes e no botão Selecionar arquivo para importar dados do site carregando um. tsv ou um arquivo. csv.](media/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
Se você for um Skype para administração de negócios, você pode usar um arquivo de dados existente do Skype para Business Online chamada qualidade Dashboard. Primeiro, você baixe o arquivo do painel de controle de qualidade de chamada e, em seguida, você o carrega no Analytics chamada. Para baixar um arquivo de dados existente, vá para o **Skype para Business Admin center** > **Ferramentas** > **Skype para negócios Online chamada qualidade painel** > **Carregar Agora**. Na lista **Meus carregamentos** , clique em **Baixar** ao lado do arquivo que você deseja.
  
Se você estiver criando o arquivo. csv ou. tsv desde o início, consulte o [formato e a estrutura do arquivo de dados de criação do arquivo de dados de Inquilino](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Tópicos relacionados
<a name="BKMK_UploadFiles"> </a>

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade das chamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de chamada e o painel de controle de qualidade de chamada](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
