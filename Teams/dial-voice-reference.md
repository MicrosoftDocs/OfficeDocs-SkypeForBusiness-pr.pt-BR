---
title: Referência de reconhecimento de voz e discagem de fila de chamadas e atendimento automático
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Saiba mais sobre as opções de discagem automática de fila de chamadas e reconhecimento de voz no Teams.
ms.openlocfilehash: 1cb8da2d2e6625de5a1471d1051c1ca51f11bbae
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918957"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Referência de reconhecimento de voz e discagem de fila de chamadas e atendimento automático

Discar por Nome é um recurso de um assistente automático que também é conhecido como pesquisa de diretório. Ele permite que as pessoas que liguem para o seu atender automático usem as respostas de voz (reconhecimento de fala) ou do teclado de telefone (DTMF) para inserir um nome completo ou parcial para pesquisar o diretório da empresa, localizar a pessoa e, em seguida, transferir a chamada para ela. Configure a discagem por nome ao configurar as configurações de fluxo [de chamada em um atendimento automático.](create-a-phone-system-auto-attendant.md#call-flow)

## <a name="searching-for-users"></a>Pesquisando usuários

Os usuários que você deseja localizar e acessar usando o Recurso Discar por Nome não precisam ter um número de telefone ou ter Planos de Chamada atribuídos a eles, mas devem estar habilitados para usuários do Enterprise Voice do **Skype for Business Server.** O discar por Nome ainda poderá encontrar e transferir chamadas para usuários do Microsoft Teams hospedados em diferentes países ou regiões para organizações multinacionais. De acordo com os pré-requisitos envolvidos, você habilita explicitamente o Discar por Nome em um atendimento automático.

Discar por extensão é um recurso de um assistente automático que também faz parte da pesquisa de diretório. Ele permite que as pessoas que liguem para o seu atender automático usem respostas de voz (reconhecimento de fala) ou do teclado de telefone (DTMF) para inserirem a extensão de telefone do usuário que estão tentando contabilitar e, em seguida, transferirem a chamada para eles. Os usuários que você deseja localizar e acessar usando o Discar por extensão não são necessários para ter um número de telefone ou ter Planos de Chamada atribuídos a eles, mas eles devem estar habilitados para o Enterprise Voice para usuários do **Skype for Business Server.** Você também precisará ter um plano de discagem configurado adequadamente para seus usuários. O discar por extensão ainda poderá encontrar e transferir chamadas para usuários do Microsoft Teams hospedados em diferentes países ou regiões para organizações multinacionais. Considerando os pré-requisitos envolvidos, você habilita explicitamente o Discar por extensão em um atendimento automático.

### <a name="maximum-directory-size"></a>Tamanho máximo do diretório

Não há limite para o número de usuários do Active Directory Discar por Nome e Discar por Extensão pode ser suportado quando um chamador procura uma pessoa específica. Um chamador pode inserir nomes parciais ou completos (Nome + Sobrenome e também Sobrenome + Nome), mas precisa do número completo da extensão. O tamanho máximo da lista de nomes que um único assistente automático pode dar suporte usando o reconhecimento de fala é de 80.000 usuários.
  
|Tipo de entrada|Formato de pesquisa|Número máximo de usuários em uma organização|
|:-----|:-----|:-----|
|DTMF (entrada de teclado) |Parcial  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome |Sem limite  |
|Fala (entrada de voz) |Firstname  <br/> Lastname  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome  | 80.000 usuários |

> [!NOTE]
> Se você estiver usando Discar por Nome com reconhecimento de fala, mas o Active Directory da sua organização for maior que 80.000 usuários e você não tiver limitado o escopo de Discar por Nome usando o recurso Escopo de Discagem, Discar por Nome ainda funcionará para os chamadores usando um teclado de telefone e as entradas de voz estarão disponíveis para todos os outros cenários. Você pode usar o recurso Escopo de Discagem para restringir os nomes que são acessíveis mudando o escopo da Discagem por Nome para um atendedor automático específico.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>Discar por Nome - entrada de teclado (DTMF)
As pessoas que ligarem podem usar o Discar por Nome para entrar em contato com os usuários especificando o nome completo ou parcial da pessoa que estão tentando entrar em contato. Há vários formatos que podem ser usados quando o nome é inserido.

Ao pesquisar o diretório de sua organização, as pessoas podem usar a tecla '0' (zero) para indicar um espaço entre o nome e o sobrenome ou sobrenome e nome. Quando eles inserirem o nome, eles serão solicitados a encerrar a entrada do teclado com a tecla #. Por exemplo, "Depois que você inserir o nome da pessoa que está tentando contatar, pressione #". Se vários nomes forem localizados, a pessoa que liga receberá uma lista de nomes para escolher.
  
As pessoas podem pesquisar os nomes em sua organização usando os seguintes formatos de pesquisa em seu teclado de telefone:
  
|Formato de nome|Tipo de pesquisa|Exemplo|Resultado de pesquisa|
|:-----|:-----|:-----|:-----|
|Nome + Sobrenome |Completo  |Amos0Marble# |Amos Marble |
|Sobrenome + Nome |Completo |Marble0Amos#  |Amos Marble |
|Firstname  |Completo   |Amos#   |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |
|Lastname |Completo |Marble#  |Pressione 1 para Amos Marble  <br/> Pressione 2 para Mary Marble |
|Nome ou Sobrenome |Parcial |Mar# |Pressione 1 para Mary Marble  <br/> Pressione 2 para Mary Jones  <br/> Pressione 3 para Amos Marcus |
|Nome + Sobrenome |Parcial |Amos0Mar # |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |
|Sobrenome + Nome |Parcial |Mar0Am# |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |

Há vários caracteres especiais que são usados durante a pesquisa de pessoas por meio de um teclado de telefone. Por exemplo, a pessoa será solicitado a usar a tecla pound (#), enquanto a tecla zero (0) é usada para um espaço entre nomes. Pressionar a tecla asterisco (*) repetirá a lista de nomes correspondentes para a pessoa.
  
|Caractere de teclado de telefone especial|O que significa|
|:-----|:-----|
|#   |Caractere final ao inserir um nome. |
|0   |Espaço entre nomes. |
|*    |Repetir a lista de nomes correspondentes. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Discar por Nome - Reconhecimento de nome pela fala

As pessoas podem procurar outras pessoas em sua organização com voz (reconhecimento de fala). Eles também podem entrar em contato com qualquer pessoa no Active Directory dizendo o nome completo ou parcial da pessoa que estão tentando localizar. O uso de entradas de voz pode reconhecer nomes em vários formatos, incluindo Nome, Sobrenome, Nome + Sobrenome ou Sobrenome + Nome.
  
Você pode habilitar o reconhecimento de fala para um atender automático, mas a entrada do teclado de telefone (DTMF) não está desabilitada. A entrada do teclado de telefone pode ser usada a qualquer momento, mesmo que o reconhecimento de fala seja habilitado no atender automaticamente.
  
Como na entrada do teclado do telefone, se vários nomes são encontrados, a pessoa que liga ouve uma lista de nomes para selecionar.
  
Os chamadores podem dizer nomes nos seguintes formatos:
  
|Nome com fala|Tipo de pesquisa|Exemplo|Resultado de pesquisa|
|:-----|:-----|:-----|:-----|
|Nome + Sobrenome |Completo |Amos Marble |Amos Marble |
|Sobrenome + Nome |Completo  |Marble Amos |Amos Marble |
|Firstname |Completo |Amos |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Amos Jones |
|Lastname |Completo |Marble |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Ben Marble |
|Nome ou Sobrenome |Parcial |Março |Pressione ou diga 1 para Mary Marble  <br/> Pressione ou diga 2 para Mary Jones  <br/> Pressione ou diga 3 para Amos Mark |
|Nome + Sobrenome |Parcial |Amos Mar |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou diga 2 para Amos Mark |


> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório para Discar por Nome com reconhecimento de fala devido ao atraso de replicação do Active Directory.
  
## <a name="language-support"></a>Suporte a idiomas

Os seguintes idiomas estão disponíveis para texto em fala usados com prompts de saída:
  
|-|-|-|
|:-----|:-----|:-----|
|Árabe (EG)  |Inglês (NZ)  |Coreano (KO)  |
|Chinês (HK)  |Inglês (Reino Unido) |Noruega (NO)  |
|Chinês (TW) |Inglês (EUA) |Polonês (PL)  |
|Chinês (ZH) |Finlandês (FI) |Português (BR) |
|Dinamarquês (DA)  |Francês (CA)  |Português (PT) |
|Holandês (NL)   |Francês (FR)  |Russo (RU) |
|Inglês (AU)  |Alemão (DE) |Espanhol (ES)  |
|Inglês (CA)  |Italiano (IT) |Espanhol (MX)|
|Inglês (IN)  |Japonês (JP) |Sueco (SV)|

A entrada de reconhecimento de fala para os participantes automáticos está disponível nos seguintes idiomas:
  
|-|-|
|:-----|:-----|
|Chinês (ZH)  |Francês (FR)  |
|Inglês (AU)  |Alemão (DE)  |
|Inglês (CA)  |Italiano (IT)  |
|Inglês (IN)  |Japonês (JP)  |
|Inglês (Reino Unido)  |Português (BR)  |
|Inglês (EUA)  |Espanhol (ES)  |
|Francês (CA)   |Espanhol (MX)  |

Os seguintes comandos de voz estão disponíveis nos 14 idiomas com suporte para reconhecimento de fala:
  
|Comando de voz| Corresponde a |
|:-----|:-----|
|Sim | Pressione 1 para Sim. |
|Não | Pressione 2 para Não. |
|Repetir |Repete a lista de opções. Pressione * no teclado para repetir a lista de opções. |
|Operador | Pressione 0 para "Operador" |
|Menu Principal  |Leva o chamador para o menu principal do atendedor automático. |
|Zero | Pressione 0 (por padrão, mesmo que "Operador").|
|Um | Pressione 1. |
|Dois | Pressione 2. |
|Três| Pressione 3.|
|Quatro | Pressione 4. |
|Cinco | Pressione 5. |
|Seis  | Pressione 6. |
|Sete | Pressione 7.|
|Oito |Pressione 8.|
|Nove  |Pressione 9.|

## <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
