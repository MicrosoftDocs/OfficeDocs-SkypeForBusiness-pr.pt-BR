---
title: Referência de discagem de fila de chamada e atendimento automático e reconhecimento de voz
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Saiba mais sobre as opções de discagem de fila de chamadas e atendimento automático e reconhecimento de voz Teams.
ms.openlocfilehash: db9eb9b4a31bd4d78c2e2519943cb405022e9fc6
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711275"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Referência de discagem de fila de chamada e atendimento automático e reconhecimento de voz

Dial by Name ou Extension é um recurso de atendimento automático que permite que os chamadores cheguem Teams usuários em sua organização. Usar seus chamadores de teclado de voz ou telefone pode dizer ou inserir o nome completo ou parcial ou extensão da pessoa que eles gostaria de alcançar. O atendente automático pesquisará o diretório da empresa, localizará a pessoa e, em seguida, transferirá o chamador para ela.  Discar por Nome ou Discar por Extensão são opções configuradas quando você configura as configurações de fluxo [de chamada em um atendimento automático](create-a-phone-system-auto-attendant.md#call-flow).


## <a name="searching-for-users"></a>Pesquisar usuários

Teams usuários que podem ser atingidos usando Discagem por Nome não são necessários para ter um número de telefone ou ter Planos de Chamadas atribuídos **a eles,** mas eles devem estar Enterprise Voice habilitados para Skype for Business Server usuários. Para organizações multi-nacionais, Dial by Name encontrará e transferirá chamadores para Microsoft Teams usuários que estão em diferentes países ou regiões.

Teams usuários que podem ser atingidos usando Discagem por Extensão não são necessários para ter um número de telefone ou ter Planos de Chamadas atribuídos **a eles,** mas eles devem ser Enterprise Voice habilitados para usuários Skype for Business Server. Você também precisará ter um plano de discagem configurado adequadamente para seus usuários. Para organizações multi-nacionais, o Dial by Extension encontrará e transferirá chamadores para Microsoft Teams usuários que estão em diferentes países ou regiões. 

Considerando os pré-requisitos envolvidos, Discar por Nome ou Extensão deve ser explicitamente habilitado ao configurar um atendimento automático.

### <a name="maximum-directory-size"></a>Tamanho máximo do diretório

Não há limite para o número de usuários do Active Directory Discar por Nome e Discar por Extensão pode dar suporte quando um chamador pesquisa por uma pessoa específica. Um chamador pode inserir nomes parciais ou completos (FirstName + LastName e também LastName + FirstName), mas precisa do número de extensão completo. O tamanho máximo da lista de nomes que um único atendimento automático pode suportar usando o reconhecimento de fala é de 80.000 usuários.
  
|Tipo de entrada|Formato de pesquisa|Número máximo de usuários em uma organização|
|:-----|:-----|:-----|
|DTMF (entrada de teclado) |Parcial  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome |Sem limite  |
|Fala (entrada de voz) |FirstName  <br/> LastName  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome  | 80.000 usuários |

> [!NOTE]
> Se você estiver usando Dial by Name com reconhecimento de fala, mas o Active Directory da sua organização for maior que 80.000 usuários e você não tiver limitado o escopo de Discagem por Nome usando o [](create-a-phone-system-auto-attendant.md#dial-scope) recurso Escopo de Discagem, Dial by Name ainda funcionará para seus chamadores usando um teclado de telefone e as entradas de voz estarão disponíveis para todos os outros cenários. Você pode usar o recurso Escopo de Discagem para restringir os nomes que são acessíveis mudando o escopo da Discagem por Nome para um atendedor automático específico.
 
### <a name="search-considerations"></a>Considerações sobre pesquisa 
Dial by Name pesquisa primeiro o diretório de toda a organização antes de aplicar qualquer Lista de Inclusão ou Exclusão de Escopo de Discagem que tenham sido configuradas. Se a pesquisa inicial em relação ao diretório inteiro retornar mais de 100 usuários, as listas de Escopo de Discagem não serão aplicadas, a pesquisa falhará e o chamador será informado de que muitos nomes foram encontrados.
 
 
## <a name="dial-by-name---keypad-dtmf-entry"></a>Discar por Nome - entrada de teclado (DTMF)
As pessoas que estão ligando podem usar Dial by Name para chegar aos usuários especificando o nome completo ou parcial da pessoa que estão tentando alcançar. Há vários formatos que podem ser usados quando o nome é inserido.

Ao pesquisar o diretório de sua organização, as pessoas podem usar a tecla '0' (zero) para indicar um espaço entre o nome e o sobrenome ou sobrenome e nome. Quando eles estão inserindo o nome, eles serão solicitados a encerrar a entrada do teclado com a tecla #. Por exemplo, "Depois que você inserir o nome da pessoa que está tentando contatar, pressione #". Se vários nomes forem localizados, a pessoa que liga receberá uma lista de nomes para escolher.

> [!NOTE]
> Se mais de 5 nomes permanecerem após a aplicação de listas Incluir ou Excluir escopo de discagem, a pesquisa falhará e o chamador será informado de que muitos nomes foram encontrados. 
  
As pessoas podem pesquisar os nomes em sua organização usando os seguintes formatos de pesquisa em seu teclado de telefone:
  
|Formato de nome|Tipo de pesquisa|Exemplo|Resultado de pesquisa|
|:-----|:-----|:-----|:-----|
|Nome + Sobrenome |Completo  |Amos0Marble# |Amos Marble |
|Sobrenome + Nome |Completo |Marble0Amos#  |Amos Marble |
|FirstName  |Completo   |Amos#   |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |
|LastName |Completo |Marble#  |Pressione 1 para Amos Marble  <br/> Pressione 2 para Mary Marble |
|Nome ou Sobrenome |Parcial |Mar# |Pressione 1 para Mary Marble  <br/> Pressione 2 para Mary Jones  <br/> Pressione 3 para Amos Marcus |
|Nome + Sobrenome |Parcial |Amos0Mar # |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |
|Sobrenome + Nome |Parcial |Mar0Am# |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |

Há vários caracteres especiais que são usados durante a pesquisa de pessoas por meio de um teclado de telefone. Por exemplo, a pessoa será solicitado a usar a chave de libra (#), enquanto a tecla zero (0) é usada para um espaço entre nomes. Pressionar a tecla asterisco (*) repetirá a lista de nomes correspondentes para a pessoa.
  
|Caractere de teclado de telefone especial|O que significa|
|:-----|:-----|
|#   |Caractere final ao inserir um nome. |
|0   |Espaço entre nomes. |
|*    |Repetir a lista de nomes correspondentes. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Discar por Nome - Reconhecimento de nome pela fala

As pessoas podem procurar outras pessoas em sua organização com sua voz (reconhecimento de fala). Eles também podem entrar em contato com qualquer pessoa no Active Directory dizendo o nome completo ou parcial da pessoa que está tentando localizar. O uso de entradas de voz pode reconhecer nomes em vários formatos, incluindo FirstName, LastName, FirstName + LastName ou LastName + FirstName.
  
Você pode habilitar o reconhecimento de fala para um atendimento automático, mas a entrada do teclado de telefone (DTMF) não está desabilitada. Telefone entrada do teclado pode ser usada a qualquer momento, mesmo que o reconhecimento de fala seja habilitado no atendimento automático.
  
Assim como com a entrada do teclado de telefone, se vários nomes são encontrados, a pessoa que está chamando ouvir uma lista de nomes para selecionar.

> [!NOTE]
> Se mais de 5 nomes permanecerem após a aplicação de listas Incluir ou Excluir escopo de discagem, a pesquisa falhará e o chamador será informado de que muitos nomes foram encontrados. 
  
Os chamadores podem dizer nomes nos seguintes formatos:
  
|Nome com fala|Tipo de pesquisa|Exemplo|Resultado de pesquisa|
|:-----|:-----|:-----|:-----|
|Nome + Sobrenome |Completo |Amos Marble |Amos Marble |
|Sobrenome + Nome |Completo  |Marble Amos |Amos Marble |
|FirstName |Completo |Amos |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Amos Jones |
|LastName |Completo |Marble |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Ben Marble |
|Nome ou Sobrenome |Parcial |Mar |Pressione ou diga 1 para Mary Marble  <br/> Pressione ou diga 2 para Mary Jones  <br/> Pressione ou diga 3 para Amos Marco |
|Nome + Sobrenome |Parcial |Amos Mar |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou diga 2 para Amos Marco |


> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório para Discagem por Nome com reconhecimento de fala devido ao atraso de replicação do Active Directory.
  
## <a name="language-support"></a>Suporte a idiomas

O suporte a idiomas para reconhecimento de texto para fala e fala está disponível nesses [idiomas com suporte](create-a-phone-system-auto-attendant-languages.md).

Os seguintes comandos de voz estão disponíveis para reconhecimento de fala: 
  
|Comando de voz| Corresponde a |
|:-----|:-----|
|Sim | Pressione 1 para Sim. |
|Não | Pressione 2 para Não. |
|Repetir |Repete a lista de opções. Pressione * no teclado para repetir a lista de opções. |
|Operador | Pressione 0 para "Operador" |
|Menu Principal  |Leva o chamador para o menu principal do atendedor automático. |
|Zero | Pressione 0 (por padrão, o mesmo que "Operador").|
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

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](./getting-service-phone-numbers.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
