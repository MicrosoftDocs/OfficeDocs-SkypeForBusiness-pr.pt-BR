---
title: "Configurar o Skype para a análise de chamadas de negócios"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
description: "Set up and use Call Analytics to identify and troubleshoot Skype for Business and Microsoft Teams call quality problems."
---

# Configurar o Skype para a análise de chamadas de negócios

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Como um administrador de Skype for Business Online, você pode usar a análise de chamada para solucionar Skype for BusinessMicrosoft Teams chamada qualidade e conexão problemas e. Você talvez seja útil configurar os seguintes recursos na análise de chamada:
  
- Definir permissões que permitir que outras pessoas, como agentes de suporte técnico, usam a análise de chamadas, mas impedir que eles acessem o restante do Centro de administração do Skype for Business.
    
- Adicione construção, sites e informações de locatário a análise de chamar carregar um arquivo de dados. tsv ou. csv.
    
> [!NOTE]
> Análise de chamada está sendo preview. Texto e imagens descritas aqui podem não coincidir com sua experiência. 
  
## Definir permissões de análise de chamadas
<a name="BKMK_SetCAPerms"> </a>

Como administrador, você tem acesso total a todos os recursos de análise de chamadas. Além disso, você pode usar um modelo de suporte técnico no Analytics chamar que inclui grupos de permissão de nível 1 e nível 2. Usuários com permissões de nível 1 podem acessar apenas um modo de exibição limitado de análise de chamadas. Usuários com permissões de nível 2 podem acessar a funcionalidade total de análise de chamadas. Os dois níveis de permissão impedem o acesso ao restante do Centro de administração do Skype for Business. Você pode conceder acesso para as camadas, adicionando um grupo que contém o usuário para o nível 1 ou seção de nível 2 da página de permissões. Para obter detalhes, consulte [Configurar permissões hierárquicos na análise de chamadas](fbf7247a-84ae-46cc-9204-2c45b1c734cd.md#BKMK_SetUpTier).
  
Os agentes de suporte técnico de nível 1 lidar com problemas de qualidade da chamada básicos. Agentes de nível 1 não investigar problemas com reuniões; eles coletam informações relacionadas e, em seguida, escalonar a um agente de nível 2. Agentes de nível 2 ver informações de logs de chamada detalhadas ocultos de agentes de nível 1. A tabela a seguir fornece uma visão geral de informações disponíveis a agentes usando a análise de chamadas.
  
|
|
|**Atividade**|**Informações em análise de chamada**|**O que vê o agente de nível 1**|**O que vê o agente de nível 2**|
|:-----|:-----|:-----|:-----|
|**Chamadas** <br/> |Nome do chamador  <br/> |Somente o nome do usuário para os quais o agente pesquisado.  <br/> |Nome de usuário.  <br/> |
||Nome do destinatário  <br/> |Mostra como usuário interno ou usuário externo.  <br/> |Nome do destinatário.  <br/> |
||Número de telefone do chamador  <br/> |Número de telefone inteiro, exceto os três últimos dígitos são ofuscadas com símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |Número de telefone inteiro, exceto os três últimos dígitos são ofuscadas com símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |
||Número de telefone do destinatário  <br/> |Número de telefone inteiro, exceto os três últimos dígitos são ofuscadas com símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |Número de telefone inteiro, exceto os três últimos dígitos são ofuscadas com símbolos de asterisco. Por exemplo, 15552823 * * *.  <br/> |
||**Detalhes de chamadas** > guia **Avançado** <br/> |Informações não mostradas.  <br/> |Todos os detalhes exibidos, como nomes de dispositivo, endereço IP, mapeamento de sub-rede e muito mais.  <br/> |
||**Detalhes de chamadas** > **Avançado** > guia **Depurar** <br/> |Informações não mostradas.  <br/> |Todos os detalhes exibidos, como sufixo DNS e SSID.  <br/> |
|**Reuniões** <br/> |Nomes dos participantes  <br/> |Somente o nome do usuário para os quais o agente pesquisado. Outros participantes identificados como usuário interno ou externo.  <br/> |Todos os nomes mostrados.  <br/> |
||Contagem de participantes  <br/> |Número de participantes.  <br/> |Número de participantes.  <br/> |
||Detalhes da sessão  <br/> |Detalhes da sessão mostrados com exceções. Somente o nome do usuário para os quais o agente pesquisado é mostrado. Outros participantes identificados como usuário interno ou externo. Últimos três dígitos do número de telefone ofuscadas com símbolos de asterisco.  <br/> |Detalhes da sessão mostrados. Os nomes de usuário e detalhes de sessão mostrados. Últimos três dígitos do número de telefone ofuscadas com símbolos de asterisco.  <br/> |
   
 **Configurar permissões hierárquicos na análise de chamadas**
  
1. Criar Office 365 grupos de segurança de nível 1 e nível 2 e adicione as pessoas que deseja para cada grupo. Você também pode reutilizar grupos de segurança existentes. Para obter mais informações, consulte [Criar, editar ou excluir um grupo de segurança no Centro de administração do Office 365](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).
    
2. No Centro de administração do Office 365, vá para **centros de administração** > **Skype for Business**.
    
    > [!NOTE]
    > Se você será levado no Centro de administração Skype for Business antigo, vá para a nova versão clicando em **vêm tente nosso novo centro de administração**. 
  
3. No Centro de administração Skype for Business novo, clique em **permissões**.
    
4. Adicione os grupos de segurança Office 365 às caixas de **nível 1** e **nível 2**. Você pode adicionar vários grupos para cada função.
    
     ![Screenshot shows the Permissions for Call Analytics page with the options for Tier 1 and Tier 2 permissions.](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
Usuários com qualquer um desses níveis de permissão acessam Analytics ligar via o https://adminportal.services.skypeforbusiness.com URL dedicado.
  
## Carregar um arquivo. tsv ou. csv para adicionar a criação de site e informações de locatários
<a name="BKMK_UploadFiles"> </a>

Carregar um arquivo. csv ou. tsv, você pode adicionar construção, sites e informações de locatário para a análise de chamadas. Com todas essas informações, a análise de chamada pode mapear endereços IP para locais físicos. Você ou técnicos de agentes podem encontrar essas informações úteis para ajudar a identificar tendências em problemas de chamada. Por exemplo, por que são muitos usuários no mesmo prédio tendo semelhantes chama problemas de qualidade?
  
![Screenshot shows the Sites page with values for Number of sites and Number of subnets, and the Select file button to import site data by uploading a .tsv or a .csv file.](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
Se você for um administrador de Skype for Business, você pode usar um arquivo de dados existente do Skype for Business Online painel de qualidade de chamada. Primeiro, você baixa o arquivo do painel de qualidade de chamada e depois carregá-lo para a análise de chamadas. Para baixar um arquivo de dados existente, vá para o **Skype para o Centro de administração de negócios** > **Ferramentas** > **Skype for Business Online chamar qualidade Dashboard** > **Carregar Agora**. Na lista **Meus uploads**, clique em **Baixar** ao lado do arquivo desejado.
  
Se você estiver criando o arquivo. tsv ou. csv do zero, consulte [Formato de arquivo de dados de usuário e estrutura do arquivo de dados de criação](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md#BKMK_TenantDataFile).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  
## Consulte Também
<a name="MT_Footer"> </a>

#### 

[Usar a análise de chamada solucionar má Skype para empresas a qualidade das chamadas](use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality.md)
  
[Qual é a diferença entre a análise de chamadas e o painel de qualidade de chamada?](what-s-the-difference-between-call-analytics-and-call-quality-dashboard.md)

