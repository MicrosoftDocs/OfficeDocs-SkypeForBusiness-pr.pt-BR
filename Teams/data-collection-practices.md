---
title: Práticas de coleta de dados
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
hideEdit: true
description: Saiba como a Microsoft coleta dados do censo, do uso e de erros para entender o uso e os problemas do Teams e do Skype for Business para planejar melhorias no produto.
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651220"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Práticas de coleta de dados do Skype for Business e do Microsoft Teams

O Skype for Business Server e o Skype for Business Online, junto com os aplicativos do Skype for Business e do Microsoft Teams, coletam dados para ajudar a Microsoft a entender como esses produtos estão sendo usados e quais tipos de erros, como erros de entrada, ocorreram. Essas informações nos ajudam a entender os padrões de uso, planejar novos recursos e solucionar problemas e corrigir áreas problemáticas.

Enquanto alguns dados de uso são coletados automaticamente, outros dados só podem ser coletados com a permissão do administrador e/ou usuário. A coleta de dados se enquadra nestas três categorias:

- Dados do censo

- Dados de uso

- Dados do relatório de erros

## <a name="census-data"></a>Dados do censo

Os dados do censo são adquiridos exclusivamente para fornecer, dar suporte e melhorar o Skype for Business. Microsoft Teams e o Skype for Business Online. Inclui informações ambientais, como versões do dispositivo e do sistema operacional, além das configurações regionais e de idioma. Inclui também contadores para tentativas e falhas de entrada. Aqui estão alguns exemplos específicos dos dados coletados do censo:

|**Tipo de dados**|**Exemplo**|**Anotações**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |A ID é transformada em hash duas vezes: uma vez no cliente e novamente no serviço de telemetria. O hash garante que a ID não possa ser vinculada a um usuário específico.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |A ID do dispositivo é uma GUID gerada aleatoriamente uma vez no dispositivo e enviado ao serviço de telemetria.  <br/> |

Os dados do censo NÃO contêm nenhuma informação que identifique a sua organização ou seus usuários. Confira a [Política de Privacidade do Skype for Business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para obter mais informações.

Os dados do censo são ativados por padrão e não podem ser desativados por administradores ou usuários finais.

## <a name="usage-data"></a>Dados de uso

Os dados de uso incluem informações como número de chamadas feitas, número de mensagens instantâneas enviadas ou recebidas, número de participação em reuniões, frequência de recursos usados e problemas de estabilidade.

Os dados de uso podem conter informações que identificam sua organização, como contoso.com. Aqui estão alguns exemplos específicos dos dados de uso coletados:

|**Tipo de dados**|**Exemplo**|**Anotações**|
|:-----|:-----|:-----|
|Mensagem Instantânea Enviada  <br/> |12  <br/> ||
|Mensagem Instantânea Recebida  <br/> |5  <br/> ||
|Participação em reunião (tentativas)  <br/> |5  <br/> ||
|Participação em reunião (sucesso)  <br/> |4  <br/> ||
|Minutos de chamada/reunião  <br/> |30 min  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Esse é o nome da organização registrada no Office 365 e é transmitida em texto não criptografado, o que significa que não é ocultado.  <br/> |

Os dados de uso NÃO contêm nenhuma informação que identifique os usuários.

A coleta de dados de uso está ativada por padrão, mas os administradores locais podem desativá-la usando a configuração de Política de Grupo DisableAutomaticSendTracing no Skype for Business Server. Desativar essa configuração afeta todos os usuários da organização. Confira [Configurar políticas de inicialização do cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) para obter mais informações.

Os usuários finais não podem ativar ou desativar a coleta de dados de uso.

Para o Aplicativo Reuniões do Skype e para as páginas da web do iniciador de ingresso, a maneira de controlar a telemetria é por meio desta política:

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

Essa política padrão é falsa, portanto, a coleta de telemetria fica desativada por padrão. Essa configuração é por pool e controla todos os usuários que se conectam com o Aplicativo Reuniões do Skype a uma reunião hospedada nesse servidor.

## <a name="error-reporting-data"></a>Dados do relatório de erros

Os dados do relatório de erros podem incluir informações sobre desempenho e confiabilidade, configuração do dispositivo, qualidade da conexão de rede, códigos de erro, logs de erro e exceções. Aqui estão alguns exemplos específicos de dados do relatórios de erros coletados:

|**Tipo de dados**|**Exemplo**|**Anotações**|
|:-----|:-----|:-----|
|Direção da mensagem  <br/> |Recebida  <br/> ||
|Estado de conversa  <br/> |Ocioso  <br/> ||
|ID do thread de conversa  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA==  <br/> ||
|UserID  <br/> |amosmarble <br/> |A ID é enviada em texto não criptografado, o qual o serviço de telemetria transforma em hash antes de armazená-lo  <br/> |

Os dados do relatório de erros também podem conter informações de identificação pessoal, como o endereço de IP do usuário e o protocolo SIP Uniform Resource Identifier (SIP URI). Confira a [Política de Privacidade do Skype for Business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para obter uma explicação detalhada do que é coletado.

O relatório de erros exige duas coisas:

- A configuração da Política de Grupo DisableAutomaticSendTracing é definida como False no servidor ou no centro de administração do locatário (esse é o estado padrão). Confira [Configurar políticas de inicialização do cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) para obter mais informações.
    
- Os usuários finais optam individualmente pela guia Geral (clique no ícone de engrenagem ![Um ícone que representa uma engrenagem ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) e a caixa de diálogo **Opções** é aberta com a guia **Geral** exibida) no cliente do Skype for Business.
    
 
![Captura de tela da caixa de seleção da coleta de dados na caixa de diálogo Opções](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Para o Aplicativo Reuniões do Skype, o MeetingUxEnableTelemetry também controla o relatório de erros, embora, no caso de no Windows, as configurações do Watson controla o carregamento das informações de falhas. Não há nenhuma configuração de usuário para o Aplicativo Reuniões do Skype, como você vê na caixa de diálogo do cliente da área de trabalho.

Confira [Definir opções Gerais do Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) para obter mais informações.

Você pode conferir [Configurar sua rede para o Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) para configurar sua rede.

Se você estiver usando o Microsoft 365 ou o Office 365 operado pela 21Vianet na China, confira [Configurar sua rede do Skype for Business Online operado pela 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).

## <a name="related-topics"></a>Tópicos relacionados
[Disponibilidade de audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
