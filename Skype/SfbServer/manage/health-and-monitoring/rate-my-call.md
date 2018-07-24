---
title: Taxa, minha chamada em Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Resumo: Saiba sobre o recurso de taxa de chamada Meu Skype para Business Server.'
ms.openlocfilehash: 737d6a71f6880139d558d601a14d8f76c61d80f2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989060"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>Taxa, minha chamada em Skype para Business Server
 
**Resumo:** Saiba mais sobre o recurso de taxa de chamada Meu Skype para Business Server.
  
Taxa de chamada Meu era um novo recurso do Skype para 2015 de negócios e clientes de 2016 no Windows que oferece uma maneira de obter feedback de seus usuários finais de empresas.
  
A janela de taxa de chamada My oferece um sistema de classificação "star" e tokens predefinidos para as chamadas de áudio e vídeos. Além disso, os administradores podem habilitar um campo personalizado fornecer comentários.
  
Atualmente, os dados coletados do recurso Rate My Call não estão incluídos em nenhum relatório de monitoramento existente, mas sim em um relatório de monitoramento separado. Dados são coletados nas tabelas do SQL que podem ser acessadas executando consultas SQL.
  
## <a name="rate-my-call-prerequisites"></a>Pré-requisitos do Rate My Call

Antes que os usuários na sua Skype para implantação de servidor de negócios podem acessar a funcionalidade de taxa de chamada Meu, o seguinte conjunto de componentes deve ser implantado e configurado:
  
-  Você deve ter Skype para Business Server instalado (versão 9160 ou posterior).
    
- Ter seus usuários a instalar e atualizar para a versão mais recente do Skype para negócios e também pedir que eles usem o Skype para interface de usuário de negócios.
    
- Os usuários devem ser hospedados no Skype para pool de Front End do servidor de negócios.
    
- Você deve ter um Skype para Business Server monitoramento banco de dados implantado e associado ao seu Skype para pools de servidor de negócios.
    
- Recomendamos a implantação do Painel de Qualidade da Chamada (CQD, Call Quality Dashboard).
    
## <a name="configure-rate-my-call"></a>Configurar o recurso Rate my Call

O recurso chamada de minha taxa é habilitado por padrão na política de cliente com as seguintes configurações:
  
- Taxa de porcentagem de exibição minha chamada - 10%
    
- Classifique minha chamada permitir personalizado comentários do usuário - desabilitado
    
Não há nenhuma ação é necessária para habilitar o recurso de base, no entanto, mas se desejar receber comentários personalizado, você precisará ativá-la separadamente. O seguinte cmdlet do Windows PowerShell é um exemplo de comentários do usuário personalizada do final de habilitação e alterando o intervalo de 10% para 80%.
  
```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>Acessando os dados de Rate My Call

Dados de usuários são coletados em duas tabelas do banco de dados de monitoramento.
  
 **[QoeMetrics]. dbo. [CallQualityFeedbackToken]** -Esta tabela contém os resultados da sondagem token por usuários finais.
  
 **[QoeMetrics]. dbo. [CallQualityFeedbackTokenDef]** -Esta tabela contém definições de tokens.
  
As definições do token são codificadas da seguinte forma:
  
|||
|:-----|:-----|
|1  <br/> |DistortedSpeech  <br/> |
|2  <br/> | ElectronicFeedback <br/> |
|3  <br/> | BackgroundNoise <br/> |
|4  <br/> |MuffledSpeech  <br/> |
|5  <br/> |Eco  <br/> |
|21  <br/> | FrozenVideo <br/> |
|22  <br/> | PixelatedVideo <br/> |
|23  <br/> | BlurryImage <br/> |
|24  <br/> | PoorColor <br/> |
|25  <br/> | DarkVideo <br/> |
|101  <br/> |Audio_SilentLocal  <br/> |
|102  <br/> |Audio_SilentRemote  <br/> |
|103  <br/> |Audio_Echo  <br/> |
|104  <br/> |Audio_BackgroundNoise  <br/> |
|105  <br/> |Audio_LowSound  <br/> |
|106  <br/> |Audio_Dropped  <br/> |
|107  <br/> |Audio_DistortedSpeech  <br/> |
|108  <br/> |Audio_Interrupted  <br/> |
|109  <br/> |Audio_Other  <br/> |
|201  <br/> |Video_NoLocalVideo  <br/> |
|202  <br/> |Video_NoRemoteVideo  <br/> |
|203  <br/> |Video_LowQuality  <br/> |
|204  <br/> |Video_FrozenVideo  <br/> |
|205  <br/> |Video_StoppedUnexpectedly  <br/> |
|206  <br/> |Video_DarkVideo  <br/> |
|207  <br/> |Video_NoAudioSync  <br/> |
|208  <br/> |Video_Other  <br/> |
|301  <br/> |Pstn_DialPad  <br/> |
|401  <br/> |SS_NoContentLocal  <br/> |
|402  <br/> |SS_NoContentRemote  <br/> |
|403  <br/> |SS_CantPresent  <br/> |
|404  <br/> |SS_LowQuality  <br/> |
|405  <br/> |SS_Freezing  <br/> |
|406  <br/> |SS_StoppedUnexpectedly  <br/> |
|407  <br/> |SS_LargeDelay  <br/> |
|408  <br/> |SS_Other  <br/> |
|501  <br/> |Reliabilty_Join  <br/> |
|502  <br/> |Reliabilty_Invite  <br/> |
   
 **[QoeMetrics]. dbo. [CallQualityFeedback]** Esta tabela contém os resultados de sondagem de comentários de votação e atendimento ao cliente "Estrela" se for habilitada.
  
Dados de tabelas podem ser chamados usando um **Selecione \* de [Table.Name]** consulta ou usando o Microsoft SQL Server Management Studio.
  
Podem ser usadas as seguintes consultas em SQL:
  
 **Áudio**
  
```
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
 
```

 **Vídeo**
  
```
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a>Atualizando as definições de Token

O mais recente Skype para clientes corporativos relatar novo token problema IDs (\> 100) que podem não estar presentes em seu [QoeMetrics]. dbo. Tabela [CallQualityFeedbackTokenDef]. Para atualizar a tabela de banco de dados com as definições de tokens mais recentes, o comando abaixo SQL pode ser executado no monitoramento banco de dados usando o Microsoft SQL Server Management Studio. Esse comando irá substituir todas as entradas em [QoeMetrics]. dbo. Tabela [CallQualityFeedbackTokenDef].
  
```
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');

```


