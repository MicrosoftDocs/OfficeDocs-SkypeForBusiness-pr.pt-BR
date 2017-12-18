---
title: "Usar a análise de chamada solucionar má Skype para empresas a qualidade das chamadas"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 6/22/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
description: "Use Call Analytics details about devices, networks, and connectivity to troubleshoot user problems with Skype for Business calls and meetings."
---

# Usar a análise de chamada solucionar má Skype para empresas a qualidade das chamadas

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Análise de chamada ajuda a solucionar problemas de chamada ou conexão com Skype for Business. Análise de chamada mostra informações detalhadas sobre os dispositivos, redes e conectividade a chamadas e reuniões de cada usuário em sua conta de Skype for Business. Se criando, de site e de locatários informações foram adicionadas para análise de chamada, ele também será mostrado para cada chamada e a sessão. Informações disponíveis por meio de análise de chamada podem ajudá-lo a compreender por que um usuário tinha uma chamada má ou experiência de reunião.
  
> [!NOTE]
> Análise de chamada está sendo preview. Texto e imagens descritas aqui podem não coincidir com sua experiência. 
  
## Solucionar problemas de qualidade de chamada usando a análise de chamadas

O nível de permissões atribuído a você determina o tipo de informação que você tem acesso na análise de chamada:
  
- **Skype para administração de empresas**: você tem acesso a todas as informações no Analytics chamar e no Centro de administração do Skype for Business.
    
- **Agente de assistência técnica com permissões de nível 1**: você vir um conjunto limitado de dados em análise de chamadas. Você pode solucionar chamadas, mas você vai entregar problemas com reuniões para um agente de nível 2. Você não tem acesso ao restante do Centro de administração do Skype for Business.
    
- **Agente de assistência técnica com permissões de nível 2**: ver todos os dados disponíveis em análise de chamadas e pode ajudar a solucionar problemas com chamadas e reuniões. Você não tem acesso ao restante do Centro de administração do Skype for Business.
    
Consulte seu administrador de Skype for Business se precisar de ajuda com permissões.
  
 **Abra a análise de chamada como um agente de suporte técnico de nível 1 ou nível 2**
  
1. Vá para [https://adminportal.services.skypeforbusiness.com](https://adminportal.services.skypeforbusiness.com)e, em seguida, entre com seu nome de usuário e senha.
    
2. Em **Pesquisa de usuário**, comece a digitar o endereço sip ou o nome do usuário cujas chamadas que você deseja solucionar e, em seguida, selecione o usuário na lista.
    
    ![Screenshot of the User Search box of Call Analytics in the Skype for Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. No **histórico de chamadas**, selecione chamada ou reunião que você deseja solucionar.
    
    ![Screenshot shows the call history page for a user with information such as the user's contact details, a summary of the 7-day quality and activity for meetings and calls, and an overview of dates and times, recipients, and audio quality,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. Selecione a guia **Avançado** e, em seguida, procure por itens amarelos e vermelhos que indicam problemas de qualidade ou conexão de chamada má.
    
    Na seção detalhes da sessão para cada chamada ou reunião, pequenos problemas aparecem em amarelo. (Por exemplo, a captura de tela seguinte, os valores são em amarelo para variação média, Max variação e taxa de perda de pacote média.) Se algo estiver amarelo, ele está fora do intervalo normal e ele pode ser contribuem para o problema, mas é provável a causa principal do problema. Se algo estiver vermelho, é um problema significativo, e é provável a causa principal da chamada de má qualidade para esta sessão.
    
    ![Screenshot shows the Advanced tab of a user's Call history with the Inbound network section expanded to reveal that the data for average jitter, max jitter, and average packet loss rate are shown in a yellow color, meaning they are minor issues.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
Em casos raros, qualidade da experiência de dados não for recebida para sessões de áudio. Geralmente, isso é causado pela chamada soltar e conexão com o cliente encerrando. Quando isso ocorre, a classificação de sessão é "indisponível".
  
Para sessões de áudio que têm a qualidade dos dados de experiência (QoE), a tabela a seguir descreve problemas principais que qualificar uma sessão como "ruim".
  
|**Problema**|**Área**|**Descrição**|
|:-----|:-----|:-----|
|Configuração de chamada  <br/> |Sessão  <br/> |O código de erro Ms-diagnóstico 20-29 indica falha de configuração da chamada. O usuário não foi possível ingressar chamada ou reunião.  <br/> |
|Rede de áudio classificados chamada ruim  <br/> |Sessão  <br/> |Problemas de qualidade da rede foram encontrados em áreas como perda de pacotes, variação, degradação NMOS, tempo de resposta, ou ocultos proporção. Para obter mais informações sobre as condições usado para classificar má chamadas, consulte esta [postagem de blog Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Dispositivo não funcionando  <br/> |Dispositivo  <br/> | Um dispositivo não está funcionando corretamente. Dispositivo não funcionando taxas é: <br/>  DeviceRenderNotFunctioningEventRatio > = 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0,005 <br/> |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  
## Consulte Também
<a name="MT_Footer"> </a>

#### 

[Configurar o Skype para a análise de chamadas de negócios](set-up-skype-for-business-call-analytics.md)

