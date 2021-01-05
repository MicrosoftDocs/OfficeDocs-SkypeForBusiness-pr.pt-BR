---
title: Atendedor automático e discagem da fila de chamadas e referência do reconhecimento de voz
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
description: Saiba mais sobre as opções atendedor automático e discagem da fila de chamadas e reconhecimento de voz no Teams.
ms.openlocfilehash: 4ff2e60a1d785a035ee20c6547108f1b8916bcfb
ms.sourcegitcommit: 7c6a9e851d2fbf055d15e681e367d9dceee0b917
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749440"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Atendedor automático e discagem da fila de chamadas e referência do reconhecimento de voz

Discar por nome é um recurso de um atendedor automático que também é conhecido como pesquisa de diretório. Ele permite que as pessoas que chamam seu atendedor automático usem voz (reconhecimento de fala) ou as respostas do teclado de telefone (DTMF) para inserir um nome completo ou parcial para pesquisar o diretório da empresa, localizar a pessoa e fazer com que a chamada seja transferida para ela. Você configura o recurso discar por nome ao [definir as configurações de fluxo de chamadas em um atendedor automático](create-a-phone-system-auto-attendant.md#call-flow).

## <a name="searching-for-users"></a>Procurando usuários

Os usuários que você quer localizar e chegarem usando o recurso discar por nome **não devem ter um número de telefone ou ter planos de chamada atribuídos a eles, mas devem ter o Enterprise Voice habilitado para usuários do Skype for Business Server**. Discar por nome poderá, até mesmo, localizar e transferir chamadas para os usuários do Microsoft Teams que são hospedados em diferentes países ou regiões para organizações multinacionais. Devido aos pré-requisitos envolvidos, você habilitou explicitamente o recurso discar por nome em um atendedor automático.

Discar por extensão é um recurso de um atendedor automático que também faz parte da pesquisa de diretório. Ele permite que as pessoas que chamam seu atendente automático usem voz (reconhecimento de fala) ou as respostas do teclado de telefone (DTMF) para inserir a extensão de telefone do usuário para o qual estão tentando falar e, em seguida, fazer com que a chamada seja transferida para elas. Os usuários que você quer localizar e acessados usando o recurso discar por  **não devem ter um número de telefone ou ter planos de chamada atribuídos a eles, mas devem ter o Enterprise Voice habilitado para usuários do Skype for Business Server**. Você também precisará ter um plano de discagem configurado adequadamente para seus usuários. A discagem por extensão poderá até mesmo localizar e transferir chamadas para os usuários do Microsoft Teams que são hospedados em diferentes países ou regiões para organizações multinacionais. Devido aos pré-requisitos envolvidos, você habilitou explicitamente a extensão dial by em um atendedor automático.

### <a name="maximum-directory-size"></a>Tamanho máximo do diretório

Não há limite quanto ao número de usuários do Active Directory discados por nome e discar por extensão pode oferecer suporte quando um chamador pesquisar por uma pessoa específica. Uma chamada pode inserir nomes parciais ou completos (nome + sobrenome e também sobrenome + nome), mas precisa do número de ramal completo. O tamanho da lista de nomes máximo que um único atendedor automático pode oferecer suporte usando o reconhecimento de fala é de 80.000 usuários.
  
|Tipo de entrada|Formato de pesquisa|Número máximo de usuários em uma organização|
|:-----|:-----|:-----|
|DTMF (entrada de teclado) |Parcial  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome |Sem limite  |
|Fala (entrada de voz) |Nome  <br/> Apelido  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome  | usuários do 80.000 |

> [!NOTE]
> Se você estiver usando discar por nome com reconhecimento de fala, mas o Active Directory da sua organização for maior do que o 80.000 usuários e você não tiver limitado o escopo de discagem por nome usando o recurso de escopo de discagem, a discagem por nome ainda funcionará para seus chamadores usando um teclado de telefone, e as entradas de voz estarão disponíveis para todos os outros cenários. Você pode usar o recurso Escopo de Discagem para restringir os nomes que são acessíveis mudando o escopo da Discagem por Nome para um atendedor automático específico.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>Discar por Nome - entrada de teclado (DTMF)
As pessoas que fazem chamadas podem usar o recurso discar por nome para acessar os usuários especificando o nome completo ou parcial da pessoa que estão tentando acessar. Há vários formatos que podem ser usados quando o nome é inserido.

Ao pesquisar o diretório de sua organização, as pessoas podem usar a tecla '0' (zero) para indicar um espaço entre o nome e o sobrenome ou sobrenome e nome. Quando eles estiverem inserindo o nome, será solicitado que ele encerre a entrada do teclado com a tecla #. Por exemplo, "Depois que você inserir o nome da pessoa que está tentando contatar, pressione #". Se vários nomes forem localizados, a pessoa que liga receberá uma lista de nomes para escolher.
  
As pessoas podem pesquisar os nomes em sua organização usando os seguintes formatos de pesquisa em seu teclado de telefone:
  
|Formato de nome|Tipo de pesquisa|Exemplo|Resultado de pesquisa|
|:-----|:-----|:-----|:-----|
|Nome + Sobrenome |Completo  |Amos0Marble# |Amos Marble |
|Sobrenome + Nome |Completo |Marble0Amos#  |Amos Marble |
|Nome  |Completo   |Amos#   |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |
|Apelido |Completo |Marble#  |Pressione 1 para Amos Marble  <br/> Pressione 2 para Mary Marble |
|Nome ou Sobrenome |Parcial |Mar# |Pressione 1 para Mary Marble  <br/> Pressione 2 para Mary Jones  <br/> Pressione 3 para Amos Marcus |
|Nome + Sobrenome |Parcial |Amos0Mar # |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |
|Sobrenome + Nome |Parcial |Mar0Am# |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |

Há vários caracteres especiais que são usados durante a pesquisa de pessoas por meio de um teclado de telefone. Por exemplo, a pessoa será solicitada a usar a tecla sustenido (#), enquanto a tecla zero (0) é usada para um espaço entre os nomes. Pressionar a tecla asterisco (*) repetirá a lista de nomes correspondentes para a pessoa.
  
|Caractere de teclado de telefone especial|O que significa|
|:-----|:-----|
|#   |Caractere final ao inserir um nome. |
|0   |Espaço entre nomes. |
|*    |Repetir a lista de nomes correspondentes. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Discar por Nome - Reconhecimento de nome pela fala

As pessoas podem pesquisar outras pessoas em sua organização com voz (reconhecimento de fala). Eles também podem acessar qualquer pessoa no Active Directory informando o nome completo ou parcial da pessoa que está tentando localizar. Usar entradas de voz pode reconhecer nomes em vários formatos, incluindo FirstName, LastName, FirstName + LastName ou LastName + FirstName.
  
Você pode habilitar o reconhecimento de fala para um atendedor automático, mas a entrada do teclado de telefone (DTMF) não está desabilitada. A entrada do teclado de telefone pode ser usada a qualquer momento, mesmo se o reconhecimento de fala estiver habilitado no atendedor automático.
  
Assim como na entrada do teclado de telefone, se vários nomes forem encontrados, a pessoa que está ligando ouvirá uma lista de nomes para selecionar.
  
Os chamadores podem dizer nomes nos seguintes formatos:
  
|Nome com fala|Tipo de pesquisa|Exemplo|Resultado de pesquisa|
|:-----|:-----|:-----|:-----|
|Nome + Sobrenome |Completo |Amos Marble |Amos Marble |
|Sobrenome + Nome |Completo  |Marble Amos |Amos Marble |
|Nome |Completo |Amos |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Amos Jones |
|Apelido |Completo |Marble |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Ben Marble |
|Nome ou Sobrenome |Parcial |Mar |Pressione ou diga 1 para Mary Marble  <br/> Pressione ou diga 2 para Mary Jones  <br/> Pressione ou diga 3 para Amos Marcus |
|Nome + Sobrenome |Parcial |Mar de Amos |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou diga 2 para Amos Marcus |


> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha o nome listado no diretório para discar por nome com reconhecimento de fala devido à defasagem de replicação do Active Directory.
  
## <a name="language-support"></a>Suporte a idiomas

Os seguintes idiomas estão disponíveis para conversão de texto em fala usadas com prompts de saída:
  
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

A entrada de reconhecimento de fala dos atendedores automáticos está disponível nos seguintes idiomas:
  
|-|-|
|:-----|:-----|
|Chinês (ZH)  |Francês (FR)  |
|Inglês (AU)  |Alemão (DE)  |
|Inglês (CA)  |Italiano (IT)  |
|Inglês (IN)  |Japonês (JP)  |
|Inglês (Reino Unido)  |Português (BR)  |
|Inglês (EUA)  |Espanhol (ES)  |
|Francês (CA)   |Espanhol (MX)  |

Os comandos de voz a seguir estão disponíveis nos 14 idiomas com suporte para o reconhecimento de fala:
  
|Comando de voz| Corresponde a |
|:-----|:-----|
|Sim | Pressione 1 para Sim. |
|Não | Pressione 2 para não. |
|Repetir |Repete a lista de opções. Pressione * no teclado para repetir a lista de opções. |
|Operador | Pressione 0 para "operador" |
|Menu Principal  |Leva o chamador para o menu principal do atendedor automático. |
|Zero | Pressione 0 (por padrão, o mesmo que "operador").|
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

[Exemplo de pequenas empresas - Configurar um atendedor automático](/microsoftteams/tutorial-org-aa)
