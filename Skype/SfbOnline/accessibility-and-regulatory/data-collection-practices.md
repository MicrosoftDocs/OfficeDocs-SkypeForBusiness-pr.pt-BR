---
title: "Práticas de coleta de dados"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
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
- Legal
hideEdit: 
description: "Microsoft coleta dados censo, erro e uso para entender como Skype para negócios está sendo usada e onde os usuários encontrarem problemas. Os dados são usados para planejar os aperfeiçoamentos do produto."
ms.openlocfilehash: f58a5650da1b6f489c63fdb5e5870321e0f06727
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Skype para práticas de conjunto de dados corporativos e Teams da Microsoft

Skype para Business Server 2015, Skype para negócios Online, juntamente com o Skype para aplicativos de negócios e Teams Microsoft coletar dados para ajudar a compreender como esses produtos estão sendo usados e quais tipos de erros, como erros de entrada, que ocorreram na Microsoft. Essas informações nos ajuda a entender os padrões de uso, planejar novos recursos e solucionar problemas e corrigir áreas do problema.
  
Enquanto alguns dados de uso são coletados automaticamente, outros dados possam ser coletados apenas quando o admin e/ou o usuário optar por permitir que ele. Coleta de dados se enquadra dessas três categorias:
  
- Dados Census
    
- Dados de uso
    
- Dados de relatório de erros
    
## <a name="census-data"></a>Dados Census

Dados Census são adquiridos exclusivamente para fornecer, suporte e aprimorar Skype para negócios. As equipes da Microsoft e Skype para negócios on-line. Ela inclui informações ambientais como versões de dispositivo e o sistema operacional e as configurações regionais e de idioma. Ele também inclui contadores para tentativas de entrar e falhas. Aqui estão alguns exemplos específicos dos dados census coletados:

|**Tipo de dados**|**Exemplo**|**Observações**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|Versão do sistema operacional  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |A ID é misturada duas vezes: uma vez no cliente e, novamente, o serviço de telemetria. O hash garante que a ID não pode ser vinculada a um usuário específico.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |ID do dispositivo é um GUID gerado uma vez no dispositivo e enviadas para o serviço de telemetria aleatoriamente.  <br/> |
   
Dados do Census não for contêm alguma informação que identifica a sua organização ou usuários. Consulte o [Skype para a declaração de privacidade de negócios](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) para obter mais informações.
  
Dados de censo está habilitado por padrão e não podem ser desativados por administradores ou usuários finais.
  
## <a name="usage-data"></a>Dados de uso

Dados de uso incluem informações como número de chamadas feitas, número de mensagens instantâneas enviadas ou recebidas, número de reuniões ingressado, frequência dos recursos usados e problemas de estabilidade.
  
Dados de uso deve conter informações que identifica a sua organização, por exemplo, contoso.com. Aqui estão alguns exemplos específicos dos dados de uso coletados:
  
|**Tipo de dados**|**Exemplo**|**Observações**|
|:-----|:-----|:-----|
|Mensagens Instantâneas enviadas  <br/> |12  <br/> ||
|Mensagem Instantânea recebida  <br/> |5  <br/> ||
|Ingressar em uma reunião (tentativas)  <br/> |5  <br/> ||
|Ingressar em uma reunião (sucesso)  <br/> |4  <br/> ||
|Minutos de chamada/reunião  <br/> |30 min  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Este é o nome da organização registrada no Office 365 e é transmitido em texto não criptografado, o que significa que ele não é ofuscado.  <br/> |
   
Dados de uso não for contêm alguma informação que identifica os usuários.
  
Coleta de dados de uso está habilitado por padrão, mas admins pode desativá-la usando a configuração de diretiva de grupo DisableAutomaticSendTracing em Skype para Business Server 2015 no local. Desativar essa configuração afeta todos os usuários na organização. Consulte [Configure políticas de inicialização do cliente no Skype para Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) para obter mais informações.
  
Os usuários finais não podem ativar a coleta de dados de uso ou desativar.
  
Para aplicativos do Skype reuniões e páginas da web de iniciador de ingresso, a maneira de controlar telemetria é por meio dessa diretiva:
  
Set-CsWebServiceConfiguration - MeetingUxEnableTelemetry $True
  
Essa diretiva padrão é false, portanto a coleção de telemetria está desativado por padrão. Essa configuração é por pool e controla todos os usuários que se conectam ao Skype reuniões App para uma reunião hospedada nesse servidor.
  
## <a name="error-reporting-data"></a>Dados de relatório de erros

Dados de relatório de erros podem incluir informações sobre desempenho e confiabilidade, configuração de dispositivo, qualidade da conexão de rede, códigos de erro, logs de erros e exceções. Aqui estão alguns exemplos específicos de dados coletados de relatório de erros:

|**Tipo de dados**|**Exemplo**|**Observações**|
|:-----|:-----|:-----|
|Direção da mensagem  <br/> |Entrada  <br/> ||
|Estado de conversa  <br/> |Ocioso  <br/> ||
|ID do thread de conversação  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA = =  <br/> ||
|UserID  <br/> |amosmarble <br/> |A ID é enviada em texto não criptografado, o serviço de telemetria hashes antes de armazená-lo  <br/> |
   
Dados de relatórios de erro também podem conter informações de identificação pessoal, como o endereço IP e a sessão Initiation Protocol Uniform Resource Identifier (URI do SIP) do usuário. Consulte o [Skype para a declaração de privacidade de negócios](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) para uma explicação detalhada sobre o que é coletado.
  
Relatório de erros exige duas coisas:
  
- A configuração de diretiva de grupo DisableAutomaticSendTracing ser definida como False, no servidor ou no Centro de administração de locatário (isto é o estado padrão). Consulte [Configure políticas de inicialização do cliente no Skype para Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) para obter mais informações.
    
- Os usuários finais individualmente aceitar da guia Geral (clique no ícone de engrenagem e a caixa de diálogo de opção é aberto com a guia geral exibida) o Skype para o cliente de negócios.
    
     ![Ícone de engrenagem](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype para checkbox de conjunto de dados corporativos nas opções de > diálogo geral](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Para o aplicativo do Skype reuniões, o MeetingUxEnableTelemetry também controla relatório de erro, embora para falhas no Windows, as configurações do Watson controlam informações de falha de carregamento. Não há nenhuma configuração do usuário para aplicativo de reuniões do Skype como vê na caixa de diálogo do cliente de desktop.
  
Consulte [Opções gerais definido no Skype for Business](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) para obter mais informações.
  
Você pode ver a [configurar sua rede para Skype para negócios on-line](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) para configurar sua rede.
  
Se você estiver usando o Office 365 operado pela 21Vianet na China, consulte [configurar sua rede para Skype para Business Online operado pela 21Vianet](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).
  
## <a name="related-topics"></a>Tópicos relacionados
[Programa de Aperfeiçoamento da experiência do usuário](https://www.microsoft.com/products/ceip/en-US/default.mspx)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
