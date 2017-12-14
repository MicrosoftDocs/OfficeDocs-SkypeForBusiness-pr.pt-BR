---
title: "Relatório de uso de PSTN do Skype for Business"
ms.author: tonysmit
author: tonysmit
ms.date: 11/24/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
description: "O Skype novo para área do Centro de administração de negócios relatórios mostra você chamada e áudio conferência atividade na sua organização. Ele permite que você analise relatórios para fornecer informações mais granular sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório do Skype para obter detalhes de uso de PSTN de negócios para ver o número de minutos gasto em chamadas de entrada/saída e de custo para essas chamadas. Você pode exibir detalhes de uso de PSTN de conferência de áudio, incluindo o custo da chamada para que você possa entender seu uso e detalhes de cobrança para determinar o uso de sua organização de chamadas."
---

# Relatório de uso de PSTN do Skype for Business

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](74eda791-c41f-4fd9-ae0b-913342e7ab04.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/74eda791-c41f-4fd9-ae0b-913342e7ab04). 
  
O Skype novo para área do Centro de administração de negócios **relatórios** mostra você chamada e áudio conferência atividade na sua organização. Ele permite que você analise relatórios para fornecer informações mais granular sobre as atividades de cada usuário. Por exemplo, você pode usar o relatório do **Skype para obter detalhes de uso de PSTN de negócios** para ver o número de minutos gasto em chamadas de entrada/saída e de custo para essas chamadas. Você pode exibir detalhes de uso de PSTN de conferência de áudio, incluindo o custo da chamada para que você possa entender seu uso e detalhes de cobrança para determinar o uso de sua organização de chamadas.
  
 Confira a[Relatórios de Atividade no Centro de administração do Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) para ver mais relatórios disponíveis.
  
Este relatório juntamente com o outro Skype para relatórios de negócios fornecer detalhes sobre a atividade inclusive chamar uso em toda a organização. Esses detalhes são muito útil quando você investigar, planejamento e fazer outras empresas decisões para sua organização e de configuração de [O que são créditos de comunicações?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md).
  
> [!NOTE]
> Você pode ver todos os relatórios do Skype for Business quando faz logon como administrador no Centro de administração do Office 365. 
  
## Como acessar o relatório de detalhes do uso de PSTN do Skype for Business

1. Vá para o **Centro de administração do Office 365** > clique em **centros de administração** > clique em **Skype para o Centro de administração de negócios**
    
2. Do Skype para o Centro de administração de negócios > selecionar **relatórios** no menu à esquerda e clique em **detalhes de uso PSTN.**
    
    > [!NOTE]
    > Dependendo da sua assinatura do Office 365, talvez você não veja todos os produtos e relatórios mostrados aqui. 
  
## Interpretar o relatório de uso de PSTN do Skype for Business

Você pode obter um modo de exibição para o Skype do usuário para uso de negócios PSTN examinando cada uma das colunas que são exibidas.
  
Esta é a aparência do relatório.
  
![Skype for Business PSTN usage report.](../images/d3fee22a-a163-45c5-921a-45191288e0c8.png)
  
## 

|||
|:-----|:-----|
|**1** <br/> | A tabela mostra um resumo do uso da PSTN todos por usuário. Isso mostra todos os usuários que têm o Skype for Business atribuídos a eles e seu uso PSTN. Você pode adicionar ou remover colunas à tabela. <br/> **ID de chamada** é a ID de chamada para uma chamada. É um identificador exclusivo para a chamada que é usado ao chamar suporte aos serviços Microsoft. <br/> **ID de usuário** é o nome que o usuário utiliza para entrar. <br/> **Número de telefone** é o Skype para o número de telefone comercial que recebeu a chamada para chamadas de entrada ou o número discado para chamadas de saída. <br/> **Local de usuário** é o país/região onde o usuário está localizado. <br/> **ID do chamador** é o número de telefone do chamador (ID de chamador) para chamadas de entrada, o número do qual se originou a chamada ou o Skype para número de negócios que a chamada originou chamadas de saída. <br/> **Tipo de chamada** é se a chamada foi uma PSTN entrada ou de saída de chamadas e o tipo de chamada como uma chamada colocado por um usuário ou uma conferência de áudio. Os tipos de chamada, você pode ver são: <br/> **Tipos de chamada de plano de chamada** <br/> **user_in** (o usuário recebido uma chamada de entrada de PSTN) <br/> **user_out** (o usuário colocada uma chamada de saída PSTN) <br/> **user_out_conf** (o usuário adicionado 2 ou mais participantes PSTN à chamada como uma chamada de conferência de 3-way) <br/> **user_out_transfer** (o usuário transferida a chamada para um número PSTN) <br/> **user_out_forwarding** (o usuário encaminhadas a chamada para um número PSTN) <br/> **Tipos de chamada de conferência de áudio** <br/> **conf_in** (uma chamada de entrada para a ponte de conferência de áudio) <br/> **conf_out** (uma chamada de saída da ponte de conferência de áudio geralmente para adicionar um número PSTN à conferência) <br/>  Aplicativos de comunicação unificada (UCAP) <br/> **ucap_in** (uma chamada de entrada para o aplicativo de UC como fila de chamada ou atendedor automático) <br/> **ucap_out** (uma chamada de saída do aplicativo de UC como fila de chamada ou atendedor automático) <br/> **Doméstico/internacional** informa se a chamada que foi colocada considerou internacionais (fora de um país/região) ou domésticas (dentro de um país/região) com base no local do usuário. <br/> **Destino discado** é o nome do destino do país/região que é discado como França, Alemanha ou dos Estados Unidos (EUA). <br/> **Tipo de número** é o tipo de número de telefone do número de telefone de um usuário, um número gratuito Chamada Tarifada ou serviço. <br/> **Hora de Início (UTC)** é a hora que a chamada foi iniciada ou feita. <br/> **Duração** é o tempo em que a chamada esteve conectada. <br/> **ConfID** é a ID de conferência da conferência áudio. <br/> **Encargo** é a quantidade de dinheiro ou custo da chamada que está sendo cobrado à sua conta. <br/> **Moeda** é o tipo de moeda que é usado para calcular o custo da chamada. <br/> **Recurso** é a licença usada para a chamada. Os tipos de licença, você pode ver são: <br/> **MCOPSTNPP** - créditos de comunicações <br/> **MCOPSTN1** - doméstico chamando planejar (min 3000 EUA / planos de 1200 min da UE) <br/> **MCOPSTN2** - plano de chamada internacional <br/> **MCOPSTN5** - plano de chamar domésticas (plano de chamada de 120 min) <br/> **MCOMEETADD** - conferência de áudio <br/> **MCOMEETACPEA** - pagamento por minuto conferência de áudio <br/> |
|**2** <br/> |Clique para arrastar uma coluna para **Para agrupar por uma coluna específica, arraste e solte o cabeçalho da coluna aqui** se desejar criar uma exibição que agrupe todos os dados em uma ou mais colunas. <br/> |
|**3** <br/> |Você também pode exportar os dados do relatório para um arquivo .csv do Excel. Basta clicar ou tocar no botão **Exportar para Excel**.  <br/> Isso exporta dados de todos os usuários e permite que você faça uma classificação e filtragem simples para uma análise mais detalhada. Se tiver menos de 2.000 usuários, você poderá classificar e filtrar dentro da tabela no próprio relatório. Se tiver mais de 2.000 usuários, será necessário exportar os dados para filtrar e classificar.  <br/> |
   
## Deseja ver outros relatórios do Skype for Business?

- [Relatório Atividade do Skype for Business](skype-for-business-activity-report.md) Você pode ver o quanto os seus usuários estão usando ponto-a-ponto, organizada e participou sessões de conferência.
    
- [Skype para o relatório de uso do dispositivo de negócios](skype-for-business-device-usage-report.md) Você pode para ver os dispositivos incluindo sistemas operacionais baseados no Windows e dispositivos móveis com o Skype para Business aplicativo instalados e usá-lo para mensagens Instantâneas e reuniões.
    
- [Relatório Atividade dos organizadores de conferências do Skype for Business](skype-for-business-conference-organizer-activity-report.md) Você pode ver o quanto os seus usuários estão organizando conferências que usam mensagens Instantâneas, áudio/vídeo, compartilhamento de aplicativos, Web, /dial-out - 3º festa e /dial-out - Microsoft.
    
- [Relatório Atividade de participantes de conferências do Skype for Business](skype-for-business-conference-participant-activity-report.md) Você pode ver quantas compartilhamento de aplicativo de mensagens Instantâneas, áudio/vídeo, Web e discar audioconferências estão sendo participou.
    
- [Relatório Atividade ponto a ponto do Skype for Business](skype-for-business-peer-to-peer-activity-report.md) Você pode ver o quanto os seus usuários estão usando mensagens Instantâneas, áudio/vídeo, compartilhamento de aplicativo e transferência de arquivos.
    
- [Relatório de bloqueados do Skype para usuários de negócios](skype-for-business-users-blocked-report.md) Você pode ver os usuários em sua organização que foram bloqueados façam chamadas PSTN.
    
- [Relatório de bloqueados do Skype para usuários de negócios](skype-for-business-users-blocked-report.md) Você pode ver detalhes sobre o tipo de mídia está sendo usado, a duração da sessão, o cliente usada e a URL de conferência.
    
## Tópicos Relacionados

[Relatórios de Atividade no Centro de administração do Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

