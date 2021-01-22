---
title: O que são atendedores automáticos da nuvem?
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
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
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba mais sobre atendedores automáticos da nuvem e como usá-los para permitir que os chamadores se movimentem por meio de um sistema de menus para localizar e fazer ou transferir chamadas para usuários ou departamentos.
ms.openlocfilehash: 862272ffe0cb42edc092c513823f421ab1c5bd95
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918937"
---
# <a name="what-are-cloud-auto-attendants"></a>O que são atendedores automáticos da nuvem?

O sistema de telefonia fornece atendedores automáticos, que podem ser usados para permitir que chamadores externos e internos se movimentem por meio de um sistema de menus para localizar e fazer ou transferir chamadas para usuários ou departamentos em sua organização.
  
Um atendedor automático é geralmente um nó em um sistema, dando a um chamador uma série de prompts de voz ou arquivos de áudio que eles ouvem em vez de uma operadora humana. Quando as pessoas chamam um número associado a um atendedor automático, suas opções podem redirecionar a chamada para um usuário ou localizar alguém em sua organização e, em seguida, se conectar a esse usuário. Elas podem expressar suas escolhas e interagir com o sistema de menus usando um teclado de telefone (DTMF) ou reconhecimento de fala. As opções que elas fazem também podem redirecionar a chamada para outro atendedor automático ou para uma fila de chamadas.
  
Para configurar um atendedor automático para o sistema telefônico, vá para [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md).
  
Um atendedor automático na nuvem tem os seguintes recursos:
  
- Ele oferece saudações corporativas ou informativas.
- Ele oferece menus corporativos personalizados. Você pode personalizar esses menus para ter mais do que um nível.
- Ele fornece pesquisa de diretório que permite que as pessoas liguem para pesquisar o diretório da organização em busca de um nome.
- Ele permite que alguém que ligue para alcançar ou deixar uma mensagem para uma pessoa em sua organização.
- Ele oferece suporte a vários idiomas para solicitações, conversão de texto em fala e reconhecimento de fala.
- Ele é compatível com a especificação de feriados e horários de trabalho.
- Ele permite a transferência de chamadas para um operador, outros usuários, filas de chamadas e atendedores automáticos.
- Ele dá suporte à caixa postal compartilhada para que os chamadores deixem uma mensagem para uma organização.

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.

## <a name="getting-started"></a>Introdução

Para começar a usar os atendedores automáticos, é importante lembrar-se de que:

- Um atendedor automático é necessário para ter uma conta de recurso associada. Consulte [gerenciar contas de recursos no Teams](manage-resource-accounts.md) para obter detalhes sobre contas de recursos. <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- Ao atribuir um número de telefone a um atendedor automático, você deve atribuí-lo à conta de recurso associada a esse atendedor automático. Isso fornece uma maneira de ter mais de um número de telefone acessar um atendedor automático. Na maioria das vezes, uma conta de recurso usará a licença de usuário virtual do sistema de telefone sem custo. Esta licença oferece recursos de sistema telefônico para números de telefone no nível organizacional e permite criar atendedores automáticos e filas de chamadas.

> [!NOTE]
> Os números do serviço de roteamento direto para atendedor automático e filas de chamadas são suportados somente para usuários do Microsoft Teams e para agentes de chamadas.

   > [!TIP]
   > Para redirecionar chamadas para um operador ou uma opção de menu que seja um usuário online com uma licença do **sistema de telefonia** , você precisará habilitar a conta do Enterprise Voice ou atribuir planos de chamada a elas. Consulte [atribuir licenças de Complementos do Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md). Você também pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obter e usar números de serviço de chamada gratuita para seus atendedores automáticos, você precisa configurar créditos de comunicações. Para fazer isso, confira [o que são créditos de comunicações?](what-are-communications-credits.md) e [Configure créditos de comunicações para sua organização](set-up-communications-credits-for-your-organization.md).

    > [!IMPORTANT]
    > [!IMPORTANTE] Os números de telefone (assinante) não podem ser atribuídos aos atendedores automáticos  somente números de telefone de serviço chamadas gratuitas ou tarifadas podem ser usados.

- Um sistema de atendedor automático completo geralmente envolve vários atendedores automáticos.
- É possível aplicar mais de um número de telefone a atendedores automáticos em nível de entrada.
- Os atendedores automáticos de nível não entry ou as filas de chamadas em todo o sistema precisarão apenas de um número de telefone se eles forem fazer chamadas PSTN de saída.
  
## <a name="feature-overview"></a>Visão geral do recurso

### <a name="searching-for-users"></a>Procurando usuários

Discar por nome é um recurso de um atendedor automático que também é conhecido como pesquisa de diretório. Ele permite que as pessoas que chamam seu atendedor automático usem voz (reconhecimento de fala) ou as respostas do teclado de telefone (DTMF) para inserir um nome completo ou parcial para pesquisar o diretório da empresa, localizar a pessoa e fazer com que a chamada seja transferida para ela. Os usuários que você quer localizar e acessar usando o recurso discar por nome **não devem ter um número de telefone ou ter planos de chamadas atribuídos a eles, mas devem ter uma licença de sistema telefônico se eles forem usuários online ou o Enterprise Voice estiver habilitado para usuários do Skype for Business Server**. Discar por nome poderá, até mesmo, localizar e transferir chamadas para os usuários do Microsoft Teams que são hospedados em diferentes países ou regiões para organizações multinacionais. Devido aos pré-requisitos envolvidos, você habilitou explicitamente o recurso discar por nome em um atendedor automático.

Discar por extensão é um recurso de um atendedor automático que também faz parte da pesquisa de diretório. Ele permite que as pessoas que chamam seu atendente automático usem voz (reconhecimento de fala) ou as respostas do teclado de telefone (DTMF) para inserir a extensão de telefone do usuário para o qual estão tentando falar e, em seguida, fazer com que a chamada seja transferida para elas. Os usuários que você quer localizar e se encontrarem usando o recurso discar por  **não devem ter um número de telefone ou ter planos de chamada atribuídos a eles, mas devem ter uma licença de sistema telefônico se eles forem usuários online ou Enterprise Voice habilitado para usuários do Skype for Business Server**. Você também precisará ter um plano de discagem configurado adequadamente para seus usuários. A discagem por extensão poderá até mesmo localizar e transferir chamadas para os usuários do Microsoft Teams que são hospedados em diferentes países ou regiões para organizações multinacionais. Devido aos pré-requisitos envolvidos, você habilitou explicitamente a extensão dial by em um atendedor automático.

#### <a name="maximum-directory-size"></a>Tamanho máximo do diretório

Não há limite quanto ao número de usuários do Active Directory discados por nome e discar por extensão pode oferecer suporte quando um chamador pesquisar por uma pessoa específica. Uma chamada pode inserir nomes parciais ou completos (nome + sobrenome e também sobrenome + nome), mas precisa do número de ramal completo. O tamanho da lista de nomes máximo que um único atendedor automático pode oferecer suporte usando o reconhecimento de fala é de 80.000 usuários.
  
|Tipo de entrada|Formato de pesquisa|Número máximo de usuários em uma organização|
|:-----|:-----|:-----|
|DTMF (entrada de teclado) |Parcial  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome |Sem limite  |
|Fala (entrada de voz) |Nome  <br/> Apelido  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome  | usuários do 80.000 |

> [!NOTE]
> Se você estiver usando discar por nome com reconhecimento de fala, mas o Active Directory da sua organização for maior do que o 80.000 usuários e você não tiver limitado o escopo de discagem por nome usando o recurso de escopo de discagem, a discagem por nome ainda funcionará para seus chamadores usando um teclado de telefone, e as entradas de voz estarão disponíveis para todos os outros cenários. Você pode usar o recurso Escopo de Discagem para restringir os nomes que são acessíveis mudando o escopo da Discagem por Nome para um atendedor automático específico.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Discar por Nome - entrada de teclado (DTMF)

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

#### <a name="dial-by-name---name-recognition-with-speech"></a>Discar por Nome - Reconhecimento de nome pela fala

As pessoas podem pesquisar outras pessoas em sua organização com voz (reconhecimento de fala). Eles também podem acessar qualquer pessoa no Active Directory informando o nome da pessoa que ele está tentando localizar. Usar entradas de voz pode reconhecer nomes em vários formatos, incluindo FirstName, LastName, FirstName + LastName ou LastName + FirstName.
  
Você pode habilitar o reconhecimento de fala para um atendedor automático, mas a entrada do teclado de telefone (DTMF) não está desabilitada. A entrada do teclado de telefone pode ser usada a qualquer momento, mesmo se o reconhecimento de fala estiver habilitado no atendedor automático.
  
Assim como na entrada do teclado de telefone, se vários nomes forem encontrados, a pessoa que está ligando ouvirá uma lista de nomes para selecionar.
  
Os chamadores podem dizer nomes nos seguintes formatos:
  
|Nome com fala|Tipo de pesquisa|Exemplo|Resultado de pesquisa|
|:-----|:-----|:-----|:-----|
|Nome + Sobrenome |Completo |Amos Marble |Amos Marble |
|Sobrenome + Nome |Completo  |Marble Amos |Amos Marble |
|Nome |Completo |Amos |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Amos Jones |
|Apelido |Completo |Marble |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Ben Marble |

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha o nome listado no diretório para discar por nome com reconhecimento de fala devido à defasagem de replicação do Active Directory.
  
### <a name="language-support"></a>Suporte a idiomas

Os seguintes idiomas estão disponíveis para conversão de texto em fala usadas com prompts de saída:
  
|A-E|E-J|K A Z|
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
  
|A-F|F A Z|
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

### <a name="the-operator-option"></a>A opção de operador

Um atendedor automático pode ser definido opcionalmente para dar a um chamador uma seleção para falar com uma operadora humana.
  
A chave 0 e o comando de voz "operador" direcionam a chamada para o operador designado por padrão. Esse é o caso de todos os idiomas com suporte para o reconhecimento de fala. Você também pode usar **as opções do menu definir** para definir um valor personalizado para o operador.
  
O operador pode ser definido como:
  
- Um usuário do Microsoft Teams ou um usuário do Skype for Business Server habilitado para Enterprise Voice.
- Outro atendedor automático que é configurado para sua organização.
- Qualquer fila de chamada existente que é configurada em sua organização. Para ver mais sobre filas de chamadas, consulte [criar uma fila de chamadas na nuvem](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

### <a name="business-hours-and-call-handling"></a>Horários comerciais e administração de chamada

O horário comercial pode ser definido em cada atendedor automático. Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão. O horário comercial pode ser definido com quebras de horário durante o dia, e todas as horas que não estão definidas como horário comercial são consideradas após o expediente. Você pode definir diferentes opções de tratamento de chamadas e saudações diferentes (que são opcionais) para horários comerciais e horários posteriores.
  
Cada atendedor automático tem várias opções de tratamento de chamadas possíveis:
  
- A chamada pode ser desconectada após a saudação ser reproduzida.
- Também é possível:
  - Redirecionar a chamada para um usuário do Microsoft Teams que tenha uma licença do **sistema de telefonia** compatível com o Enterprise Voice ou um plano de chamadas atribuído a ele. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para isso, selecione uma **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal.

  - Redirecionar a chamada para uma fila de chamadas. Para ver mais sobre filas de chamadas, consulte [criar uma fila de chamadas na nuvem](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

  - Redirecionar a chamada para outro atendedor automático.

Essas opções são expressas para o chamador pelo atendedor automático quando ele executa prompts de menu. Por exemplo: "Pressione 1 para Vendas, Pressione 2 para Serviços. Para falar com o operador, pressione 0 a qualquer momento."

### <a name="set-menu-options"></a>Definir opções de menu

Os atendedores automáticos da nuvem permitem criar prompts de menu ("Pressione 1 para vendas, pressione 2 para serviços") e configure as opções do menu para direcionar as chamadas com base nas seleções do usuário. As opções de menu para um atendedor automático permitem que uma organização forneça uma série de opções que orientam os chamadores para o destino mais rápido, sem depender de uma operadora de pessoas para lidar com chamadas de entrada. Os prompts de menu podem ser criados usando o recurso de conversão de texto em fala (prompts gerados pelo sistema) ou carregando um arquivo de áudio gravado. O reconhecimento de fala aceita comandos de voz para navegação viva-voz, mas as pessoas que fizerem chamadas também poderão usar o teclado numérico do telefone para navegar pelos menus.
  
As teclas de 0 a 9 podem ser atribuídas para discar as teclas em um atendedor automático usando o centro de administração do Skype for Business. Diferentes conjuntos de opções de menu podem ser criadas para os horários comerciais e horários fora do expediente, e você pode habilitar ou desabilitar o Discar por Nome nas **Opções de Menu**. As teclas podem ser mapeadas para transferir as chamadas para:
  
- Um operador, que é mapeado para a tecla 0 por padrão. No entanto, ele pode ser reatribuído a qualquer outra chave ou removido do menu.
- Uma fila de chamadas.
- Outro atendedor automático. Os menus de vários níveis podem ser configurados apontando uma **opção de menu** em um atendedor automático para outro atendedor automático com seu próprio conjunto de opções de menu, que é chamado de atendedor automático "aninhado".
- Um usuário do Microsoft Teams que tem uma licença do **sistema de telefonia** compatível com o Enterprise Voice ou tem planos de chamada atribuídos. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para isso, selecione uma **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal.
  
O nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala se o reconhecimento de fala estiver habilitado. Por exemplo, os chamadores podem dizer "um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "vendas" para selecionar a mesma opção de menu chamada "vendas".
  
Para configurar um atendedor automático e as opções de menu, vá [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md).
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Atribuindo números de telefone para um atendedor automático

Você pode atribuir um número de serviço da Microsoft, um número de roteamento direto ou um número híbrido à conta de recurso vinculado do atendente automático (ou a várias contas de recursos se for necessário mais de um número de telefone). Consulte [planejar o roteamento direto](direct-routing-plan.md) para obter mais detalhes.

Para atribuir um número de serviço, você precisará adquirir ou portar seus números de serviço de chamada tarifada ou gratuitas existentes. Depois de obter os números de telefone de serviço de chamada tarifada ou gratuita, eles aparecem nos números de telefone de voz do **centro de administração do Skype for Business**  >    >  . **Tipo de número** é listado como **serviço-chamada gratuita**. Para obter seus números de serviço, consulte [obtendo números de telefone de serviço para o Skype for Business e o Microsoft Teams](/microsoftteams/getting-service-phone-numbers) ou, se você quiser transferir e número de serviço existente, consulte [transferir números de telefone para o Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, não poderá usar o centro de administração do Microsoft Teams para obter números de serviço. Em seguida, [gerencie os números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para ver como fazê-lo.
  
## <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
