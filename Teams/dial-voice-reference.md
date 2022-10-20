---
title: Referência de reconhecimento de voz e discagem de fila de chamadas e atendedor automático
author: DaniEASmith
ms.author: danismith
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
description: Saiba mais sobre o atendedor automático e as opções de discagem de fila de chamadas e reconhecimento de voz no Teams.
ms.openlocfilehash: 3b6b1fd6932491a6f9ad17e109902484461f912f
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68613803"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Referência de reconhecimento de voz e discagem de fila de chamadas e atendedor automático

Discar por Nome ou Extensão é um recurso de atendedor automático que permite que os chamadores alcancem os usuários do Teams em sua organização. O uso de seus chamadores de teclado de voz ou telefone pode dizer ou inserir o nome completo ou parcial ou a extensão da pessoa que deseja acessar. O atendedor automático pesquisará o diretório da empresa, localizará a pessoa e transferirá o chamador para ela.  Discar por Nome ou Discar por Extensão são opções configuradas quando você define as configurações de fluxo [de chamada em um atendedor automático](create-a-phone-system-auto-attendant.md?tabs=call-flow).

## <a name="searching-for-users"></a>Pesquisando usuários

Os usuários do Teams que podem ser acessados usando Discagem por Nome não precisam ter um número de telefone ou ter Planos de Chamadas atribuídos **a eles,** mas devem estar Enterprise Voice habilitados para Skype for Business Server usuários. Para organizações multinacionais, o Dial by Name localizará e transferirá chamadores para usuários do Microsoft Teams que estão em diferentes países ou regiões.

Os usuários do Teams que podem ser acessados usando o Dial by Extension não precisam ter um número de telefone ou ter Planos de Chamadas atribuídos **a eles,** mas devem estar Enterprise Voice habilitados para Skype for Business Server usuários. Você também precisará ter um plano de discagem configurado adequadamente para seus usuários. Para organizações multinacionais, o Dial by Extension encontrará e transferirá chamadores para usuários do Microsoft Teams que estão em diferentes países ou regiões.

Considerando os pré-requisitos envolvidos, o Dial by Name ou Extension deve ser habilitado explicitamente ao configurar um atendedor automático.

### <a name="maximum-directory-size"></a>Tamanho máximo do diretório

Não há limite para o número de usuários do Active Directory Discar por Nome e Discar por Extensão pode dar suporte quando um chamador procura uma pessoa específica. Um chamador pode inserir nomes parciais ou completos (FirstName + LastName e também LastName + FirstName), mas precisa do número de extensão completo. O tamanho máximo da lista de nomes que um único atendedor automático pode dar suporte usando o reconhecimento de fala é de 80.000 usuários.
  
|Tipo de entrada|Formato de pesquisa|Número máximo de usuários em uma organização|
|:-----|:-----|:-----|
|DTMF (entrada de teclado) |Parcial  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome |Sem limite  |
|Fala (entrada de voz) |Firstname  <br/> Lastname  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome  | 80.000 usuários |

> [!NOTE]
> Se você estiver usando o Dial by Name com reconhecimento de fala, mas o Active Directory da sua organização for maior que 80.000 usuários e você não tiver limitado o escopo de Discagem por Nome usando [](create-a-phone-system-auto-attendant.md?tabs=dial-scope) o recurso Escopo de Discagem, a Discagem por Nome ainda funcionará para seus chamadores usando um teclado de telefone e as entradas de voz estarão disponíveis para todos os outros cenários. Você pode usar o recurso Escopo de Discagem para restringir os nomes que são acessíveis mudando o escopo da Discagem por Nome para um atendedor automático específico.

### <a name="search-considerations"></a>Considerações de pesquisa

O Dial by Name pesquisa primeiro o diretório de toda a organização antes de aplicar qualquer Lista de Inclusão ou Exclusão de Escopo de Discagem que tenha sido configurada. Se a pesquisa inicial em todo o diretório retornar mais de 100 usuários, as listas de Escopo de Discagem não serão aplicadas, a pesquisa falhará e o chamador será informado de que muitos nomes foram encontrados.

## <a name="dial-by-name---keypad-dtmf-entry"></a>Discar por Nome - entrada de teclado (DTMF)

Pessoas chamada pode usar Dial by Name para alcançar os usuários especificando o nome completo ou parcial da pessoa que eles estão tentando acessar. Há vários formatos que podem ser usados quando o nome é inserido.

Ao pesquisar o diretório de sua organização, as pessoas podem usar a tecla '0' (zero) para indicar um espaço entre o nome e o sobrenome ou sobrenome e nome. Quando eles estiverem inserindo o nome, eles serão solicitados a encerrar a entrada do teclado com a tecla #. Por exemplo, "Depois que você inserir o nome da pessoa que está tentando contatar, pressione #". Se vários nomes forem localizados, a pessoa que liga receberá uma lista de nomes para escolher.

> [!NOTE]
> Se mais de 5 nomes permanecerem depois que qualquer lista de Inclusão ou Exclusão de Escopo de Discagem tiver sido aplicada, a pesquisa falhará e o chamador será informado de que muitos nomes foram encontrados.
  
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

Pessoas pode pesquisar por outras pessoas em sua organização com sua voz (reconhecimento de fala). Eles também podem entrar em contato com qualquer pessoa no Active Directory dizendo o nome completo ou parcial da pessoa que está tentando localizar. O uso de entradas de voz pode reconhecer nomes em vários formatos, incluindo FirstName, LastName, FirstName + LastName ou LastName + FirstName.
  
Você pode habilitar o reconhecimento de fala para um atendedor automático, mas a entrada do teclado de telefone (DTMF) não está desabilitada. A entrada do teclado do telefone pode ser usada a qualquer momento, mesmo que o reconhecimento de fala esteja habilitado no atendedor automático.
  
Assim como acontece com a entrada do teclado do telefone, se vários nomes forem encontrados, a pessoa que está chamando ouvirá uma lista de nomes para selecionar.

> [!NOTE]
> Se mais de 5 nomes permanecerem depois que qualquer lista de Inclusão ou Exclusão de Escopo de Discagem tiver sido aplicada, a pesquisa falhará e o chamador será informado de que muitos nomes foram encontrados.
  
Os chamadores podem dizer nomes nos seguintes formatos:
  
|Nome com fala|Tipo de pesquisa|Exemplo|Resultado de pesquisa|
|:-----|:-----|:-----|:-----|
|Nome + Sobrenome |Completo |Amos Marble |Amos Marble |
|Sobrenome + Nome |Completo  |Marble Amos |Amos Marble |
|Firstname |Completo |Amos |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Amos Jones |
|Lastname |Completo |Marble |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Ben Marble |
|Nome ou Sobrenome |Parcial |Março |Pressione ou diga 1 para Mary Marble  <br/> Pressione ou diga 2 para Mary Jones  <br/> Pressione ou diga 3 para Amos Marcus |
|Nome + Sobrenome |Parcial |Amos Mar |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou diga 2 para Amos Marcus |

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório para Discar por Nome com reconhecimento de fala devido ao atraso de replicação do Active Directory.

### <a name="dial-by-extension"></a>Discar por extensão

Os usuários que você deseja disponibilizar para o **Dial By Extension** precisam ter uma extensão especificada como parte de um dos seguintes atributos de telefone definidos no Active Directory (e sincronizados por meio do Azure AD Connect) ou do Azure Active Directory. (Consulte [Adicionar usuários individualmente ou em massa](/microsoft-365/admin/add-users/add-users) para obter mais informações.)

- TelephoneNumber (AD e Azure AD)
- HomePhone (AD)
- Mobile (AD e Azure AD)
- OtherTelephone (AD)

O formato necessário para inserir a extensão no campo número de telefone do usuário pode ser um dos seguintes formatos:

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- Exemplo 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- Exemplo 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"
- Exemplo 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

Você pode definir a extensão [no Centro de administração do Microsoft 365 ou](https://admin.microsoft.com/) no centro [de administração do Azure Active Directory](https://aad.portal.azure.com). Pode levar até 12 horas para que as alterações estejam disponíveis para atendedores automáticos e filas de chamadas.

> [!NOTE]
>  Se estiver usando o campo TelephoneNumber para definir a extensão, a Microsoft recomenda que você use o formato *+\<phone number>;ext=\<extension>*. Se o usuário também receber um Número de Telefone do Teams, você deverá definir ambos os números da mesma maneira.


## <a name="language-support"></a>Suporte a idiomas

O suporte a idiomas para reconhecimento de texto em fala e fala está disponível nesses [idiomas com suporte](create-a-phone-system-auto-attendant-languages.md).

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
