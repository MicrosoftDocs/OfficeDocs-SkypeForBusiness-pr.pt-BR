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
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: true
description: A Microsoft coleta dados do censo, do uso e do erro para compreender como o Skype for Business está sendo usado e onde os usuários encontram problemas. Os dados são usados para planejar melhorias de produtos.
ms.openlocfilehash: 532cfe380a9f61043e38768c4c5d7d9c9fa8e9a6
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433387"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Práticas de coleta de dados do Skype for Business e do Microsoft Teams

O Skype for Business Server e o Skype for Business Online, juntamente com os aplicativos Skype for Business e Microsoft Teams, coletam dados para ajudar a Microsoft a entender como esses produtos são usados e quais tipos de erros, como erros de conexão, ocorreram. Essas informações nos ajudam a entender os padrões de uso, planejar novos recursos e solucionar problemas e áreas de problemas.

Enquanto alguns dados de uso são coletados automaticamente, outros dados só podem ser coletados quando o administrador e/ou o usuário optar por permitir isso. A coleta de dados se encaixa nestas três categorias:

- Dados do censo

- Dados de uso

- Dados de relatório de erros

## <a name="census-data"></a>Dados do censo

Os dados do censo são adquiridos exclusivamente para fornecer, dar suporte e melhorar o Skype for Business. Microsoft Teams e Skype for Business online. Inclui informações ambientais, como versões de dispositivos e sistemas operacionais e configurações regionais e de idioma. Ele também inclui contadores para tentativas e falhas de entrada. Aqui estão alguns exemplos específicos dos dados do censo coletados:

|**Tipo de dados**|**Exemplo**|**Observações**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|Versão do sistema operacional  <br/> |8,3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|ID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |A ID é codificada duas vezes: uma vez no cliente e novamente no serviço de telemetria. O hash garante que a identificação não pode ser vinculada a um usuário específico.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |A ID do dispositivo é um GUID gerado aleatoriamente uma vez no dispositivo e enviado ao serviço de telemetria.  <br/> |

Os dados do censo não contêm nenhuma informação que identifique sua organização ou seus usuários. Consulte a [declaração de privacidade do Skype for Business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para obter mais informações.

Os dados do censo são ativados por padrão e não podem ser desativados por administradores ou usuários finais.

## <a name="usage-data"></a>Dados de uso

Os dados de uso incluem informações como o número de chamadas feitas, o número de mensagens de chat enviadas ou recebidas, o número de reuniões associadas, a frequência de recursos usados e problemas de estabilidade.

Os dados de uso podem conter informações que identificam sua organização, como contoso.com. Veja alguns exemplos específicos dos dados de uso coletados:

|**Tipo de dados**|**Exemplo**|**Observações**|
|:-----|:-----|:-----|
|Mensagem instantânea enviada  <br/> |12  <br/> ||
|Mensagem instantânea recebida  <br/> |5  <br/> ||
|Ingressar em uma reunião (tentativas)  <br/> |5  <br/> ||
|Ingressar em uma reunião (sucesso)  <br/> |4  <br/> ||
|Minutos de chamada/reunião  <br/> |30 minutos  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Esse é o nome da Organização registrada no Office 365 e é transmitido em texto não criptografado, o que significa que não está ofuscado.  <br/> |

Os dados de uso não contêm informações que identifiquem os usuários.

A coleta de dados de uso está ativada por padrão, mas os administradores locais podem desativá-lo usando a configuração de política de grupo do DisableAutomaticSendTracing no Skype for Business Server. Desativar essa configuração afetará todos os usuários da organização. Consulte [Configurar políticas de inicialização do cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) para obter mais informações.

Os usuários finais não podem ativar ou desativar a coleta de dados de uso.

Para o aplicativo reuniões do Skype e as páginas da Web do inicializador de junção, a maneira de controlar a telemetria é por meio desta política:

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

Essa política é definida como false, portanto, a coleta de telemetria está desativada por padrão. Essa configuração é por pool e controla todos os usuários que se conectam ao aplicativo reuniões do Skype a uma reunião hospedada nesse servidor.

## <a name="error-reporting-data"></a>Dados de relatório de erros

Os dados de relatório de erros podem incluir informações sobre desempenho e confiabilidade, configuração de dispositivo, qualidade da conexão de rede, códigos de erro, logs de erros e exceções. Veja alguns exemplos específicos de dados de relatório de erros que são coletados:

|**Tipo de dados**|**Exemplo**|**Observações**|
|:-----|:-----|:-----|
|Direção da mensagem  <br/> |Chega  <br/> ||
|Estado da conversa  <br/> |Ociosidade  <br/> ||
|ID do thread da conversa  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA = =  <br/> ||
|ID  <br/> |amosmarble <br/> |A ID é enviada em texto sem formatação, que é o hash do serviço de telemetria antes de armazená-lo  <br/> |

Os dados de relatório de erros também podem conter informações de identificação pessoal, como o endereço IP do usuário e o URI de recurso Uniform Resource Identifier (SIP URI). Consulte a [declaração de privacidade do Skype for Business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para obter uma explicação detalhada do que foi coletado.

O relatório de erros requer duas coisas:

- A configuração da política de grupo DisableAutomaticSendTracing é definida como false no servidor ou no centro de administração do locatário (esse é o estado padrão). Consulte [Configurar políticas de inicialização do cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) para obter mais informações.
    
- Os usuários finais optam individualmente na guia Geral ( ![clique no ícone de engrenagem um ícone que representa um ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) engrenagem e, em seguida, a caixa de diálogo **Opções** é aberta com a guia **geral** exibida) no cliente Skype for Business.
    
 
![Captura de tela da caixa de seleção coleta de dados na caixa de diálogo opções](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Para o aplicativo reuniões do Skype, o MeetingUxEnableTelemetry também controla o relatório de erros, embora, no caso de falhas no Windows, controle as configurações do Watson carreguem informações de falha. Não há nenhuma configuração de usuário para o aplicativo reuniões do Skype como você vê na caixa de diálogo cliente da área de trabalho.

Consulte [definir opções gerais no Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) para obter mais informações.

Você pode ver [configurar sua rede para o Skype for Business online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) para configurar sua rede.

Se você estiver usando o Office 365 operado pela 21Vianet na China, consulte [configurar sua rede para o Skype for Business online operado pela 21vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).

## <a name="related-topics"></a>Tópicos relacionados
[Programa de aperfeiçoamento da experiência do usuário](https://www.microsoft.com/products/ceip/default.mspx)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
