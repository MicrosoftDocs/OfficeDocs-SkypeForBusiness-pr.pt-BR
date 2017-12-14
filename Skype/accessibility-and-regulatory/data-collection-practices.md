---
title: "Skype for Business e Teams Microsoft práticas de coleta de dados"
ms.author: tonysmit
author: tonysmit
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
description: "Microsoft collects census, usage, and error data to understand how Skype for Business is being used and where users encounter problems. The data is used to plan product improvements."
---

# Skype for Business e Teams Microsoft práticas de coleta de dados

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](c17e8ea6-b83b-4345-9401-47a6c8b13aad.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/c17e8ea6-b83b-4345-9401-47a6c8b13aad). 
  
clientes Skype for Business Server 2015, Skype for Business Online e Skype for Business coletam dados para ajudar a Microsoft a entender como esses produtos estão sendo usados e que tipos de erros, como erros de entrada, ocorreram. Essas informações nos ajudam a entender os padrões de uso, planejar novos recursos e solucionar problemas e corrigir áreas do problema.
  
Embora alguns dados de uso sejam coletados automaticamente, outros dados só podem ser coletados quando o administrador e/ou usuário permite. A coleta de dados se enquadra nessas três categorias: 
  
- Dados do censo
    
- Dados de uso
    
- Dados do relatório de erros
    
## Dados do censo

Dados de censo são adquiridos exclusivamente para fornecer, suporte e melhorar Skype for Business e Skype for Business Online. Ele inclui informações ambientais como versões de dispositivo e o sistema operacional e configurações regionais e de idioma. Ele também inclui contadores para entrar tentativas e falhas. Aqui estão alguns exemplos específicos de dados censo que são coletados:
  
|
|
|****Tipo de dados****|****Exemplo****|****Observações****|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |A ID tem hash duas vezes: uma no cliente e novamente no serviço de telemetria. O hash garante que a ID não possa ser vinculada a um usuário específico.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |A ID do dispositivo é um GUID que tem aleatoriamente gerado uma vez no dispositivo e enviadas para o serviço de telemetria.  <br/> |
   
Dados de censo não contêm qualquer informação que identifica a sua organização ou usuários. Consulte o [Skype para declaração de privacidade de negócios](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) para obter mais informações.
  
Dados do censo estão ativados por padrão e não podem ser desativados por administradores ou usuários finais.
  
## Dados de uso

Os dados de uso incluem informações como número de chamadas, número de mensagens instantâneas enviadas ou recebidas, número de reuniões das quais você participou, frequência de recursos usados e problemas de estabilidade.
  
Os dados de uso podem conter informações que identificam sua organização (por exemplo, contoso.com). Veja alguns exemplos específicos dos dados de uso que são coletados:
  
|
|
|****Tipo de dados****|****Exemplo****|****Observações****|
|:-----|:-----|:-----|
|Mensagens instantâneas enviadas  <br/> |12  <br/> ||
|Mensagens instantâneas recebidas  <br/> |5  <br/> ||
|Participar de uma reunião (tentativas)  <br/> |5  <br/> ||
|Participar de uma reunião (sucesso)  <br/> |4  <br/> ||
|Minutos de chamada/reunião  <br/> |30 min  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Este é o nome da organização registrado no Office 365 e é transmitido em texto não criptografado, o que significa que não está oculto.  <br/> |
   
Os dados de uso NÃO contêm nenhuma informação que identifica os usuários.
  
Coleta de dados de uso está ativada por padrão, mas os administradores podem desativá-lo usando a configuração de política de grupo DisableAutomaticSendTracing em Skype for Business Server 2015 no local. Desativar essa configuração afeta todos os usuários na organização. Consulte [Configurar diretivas de inicialização de cliente no Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) para obter mais informações.
  
Os usuários finais não pode ativar a coleta de dados de uso ou desativar.
  
Para o aplicativo de reuniões do Skype e páginas da web de iniciador de junção, a maneira de controlar telemetria é por meio dessa política:
  
Set-CsWebServiceConfiguration - MeetingUxEnableTelemetry $True
  
Essa política padrão é falso, para que o conjunto de telemetria está desativada por padrão. Esta configuração é por pool e controla todos os usuários que se conectam com o aplicativo de reuniões do Skype para uma reunião hospedada no servidor.
  
## Dados do relatório de erros

Os dados do relatório de erros podem incluir informações sobre desempenho e confiabilidade, configuração do dispositivo, qualidade da conexão de rede, códigos de erro, logs de erros e exceções. Veja alguns exemplos específicos de dados do relatório de erros que são coletados:
  
|
|
|****Tipo de dados****|****Exemplo****||
|:-----|:-----|:-----|
|Direção da mensagem  <br/> |Recebida  <br/> ||
|Estado da conversa  <br/> |Ocioso  <br/> ||
|ID do thread da conversa  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA==  <br/> ||
|UserID  <br/> ||A ID é enviada em texto sem criptografia, em que o serviço de telemetria executa hash antes de armazenar  <br/> |
   
Dados de relatório de erro também podem conter informações pessoalmente identificáveis como sessão inicialização protocolo Uniform Resource Identifier (URI de SIP) e o endereço IP do usuário. Consulte o [Skype para declaração de privacidade de negócios](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) para uma explicação detalhada das quais são coletadas.
  
O relatório de erros exige dois itens: 
  
- A configuração de política de grupo DisableAutomaticSendTracing ser definido como False no servidor ou no Centro de administração de locatário (Isso é o estado padrão). Consulte [Configurar diretivas de inicialização de cliente no Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) para obter mais informações.
    
- Usuários finais individualmente optar por usar na guia Geral (clique no ícone de engrenagem e a caixa de diálogo de opção é aberta com a guia geral exibida) no cliente Skype for Business.
    
     ![Ícone de engrenagem](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype for Business data collection checkbox in the Options > General dialog](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Para o aplicativo de reuniões do Skype, o MeetingUxEnableTelemetry também controla relatório de erro, embora para falhas no Windows, as configurações de Watson controlam informações de falha de carregamento. Não há nenhuma configuração de usuário para o aplicativo de reuniões do Skype como você vê na caixa de diálogo do cliente de desktop.
  
Consulte [Definir as Opções gerais do Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) para obter mais informações.
  
Você pode ver [Configurar sua rede para o Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) para configurar a rede.
  
Se você estiver usando o Office 365 operado por 21Vianet na China, consulte [Set up your network for Lync Online](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).
  
## Tópicos Relacionados

[Programa de Aperfeiçoamento da experiência do usuário](https://www.microsoft.com/products/ceip/en-US/default.mspx)
  
[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

