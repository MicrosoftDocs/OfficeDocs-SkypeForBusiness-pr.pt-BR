---
title: O que são os atendimentos automáticos na nuvem?
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
description: Saiba mais sobre os atendentes automáticos na nuvem e como usá-los para permitir que os chamadores se movam por um sistema de menus para localizar e fazer ou transferir chamadas para usuários ou departamentos.
ms.openlocfilehash: c8e5b3f608200036b8c9b9ed5338c558464b32d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100957"
---
# <a name="what-are-cloud-auto-attendants"></a>O que são os atendimentos automáticos na nuvem?

O Sistema de Telefonia fornece atendimentos automáticos, que podem ser usados para permitir que chamadores externos e internos se movam por um sistema de menus para localizar e fazer ou transferir chamadas para usuários ou departamentos em sua organização.
  
Na maioria das vezes, um atendente automático é um nó em um sistema, dando a um chamador uma série de prompts de voz ou arquivos de áudio que ouvem em vez de um operador humano. Quando as pessoas ligam para um número associado a um atendente automático, suas opções podem redirecionar a chamada para um usuário ou localizar alguém em sua organização e depois se conectar a esse usuário. Eles podem expressar suas escolhas e interagir com o sistema de menus usando um teclado de telefone (DTMF) ou reconhecimento de fala. As escolhas que eles fazem também podem redirecionar a chamada para outro atendimento automático ou para uma fila de chamada.
  
Para configurar um atendimento automático para o Sistema de Telefonia, vá para [Configurar um atendimento automático na nuvem.](create-a-phone-system-auto-attendant.md)
  
Um assistente automático na nuvem tem os seguintes recursos:
  
- Ele oferece saudações corporativas ou informativas.
- Ele oferece menus corporativos personalizados. Você pode personalizar esses menus para ter mais do que um nível.
- Ele fornece pesquisa de diretório que permite que as pessoas que ligarem pesquisem um nome no diretório da organização.
- Ele permite que alguém que liga para alcançar ou deixar uma mensagem para uma pessoa em sua organização.
- Ele oferece suporte a vários idiomas para prompts, texto para fala e reconhecimento de fala.
- Ele dá suporte à especificação de feriados e horários comerciais.
- Ele dá suporte à transferência de chamada para um operador, outros usuários, filas de chamada e atendedores automáticos.
- Ele dá suporte à caixa postal compartilhada para que os chamadores deixem uma mensagem para uma organização.

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e ao Skype for Business Online.

## <a name="getting-started"></a>Introdução

Para começar a usar os atendedores automáticos, é importante lembrar-se de que:

- Um atendente automático é necessário para ter uma conta de recurso associada. Consulte [Gerenciar contas de recursos no Teams para](manage-resource-accounts.md) obter detalhes sobre contas de recursos. <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- Ao atribuir um número de telefone a um atendente automático, estritamente falando, você está atribuindo-o à conta de recurso associada a esse atendimento automático. Isso fornece uma maneira de ter mais de um número de telefone acessando um atendimento automático. Na maioria das vezes, uma conta de recurso usará a licença de Usuário Virtual do Sistema de Telefonia gratuita. Esta licença fornece recursos do Sistema de Telefonia para números de telefone no nível organizacional e permite que você crie atendimentos automáticos e filas de chamadas.

> [!NOTE]
> Os números de serviço de Roteamento Direto para o atendimento automático e filas de chamadas são suportados apenas para usuários do Microsoft Teams e agentes de chamada.

   > [!TIP]
   > Para redirecionar chamadas para um operador ou uma  opção de menu que seja um usuário online com uma licença do Sistema de Telefonia, você precisará habilitar sua conta para Enterprise Voice ou atribuir Planos de Chamadas a eles. Consulte [Atribuir licenças de complemento do Microsoft Teams.](teams-add-on-licensing/assign-teams-add-on-licenses.md) Você também pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obter e usar números de serviço gratuitos para seus atendimentos automáticos, você precisa configurar Créditos de Comunicação. Para fazer isso, consulte [O que são Créditos de Comunicação?](what-are-communications-credits.md) e [Configurar Créditos de Comunicação para sua organização](set-up-communications-credits-for-your-organization.md).

    > [!IMPORTANT]
    > [!IMPORTANTE] Os números de telefone (assinante) não podem ser atribuídos aos atendedores automáticos  somente números de telefone de serviço chamadas gratuitas ou tarifadas podem ser usados.

- Um sistema de atendimento automático completo geralmente envolve vários atendimentos automáticos.
- É possível aplicar mais de um número de telefone aos atendentes automáticos de nível de entrada.
- Os atendimentos automáticos de nível não de entrada ou filas de chamadas no sistema completo só precisarão de um número de telefone se eles realizarem chamadas PSTN de saída.
  
## <a name="feature-overview"></a>Visão geral do recurso

### <a name="searching-for-users"></a>Pesquisar usuários

Dial by Name é um recurso de um atendimento automático que também é conhecido como pesquisa de diretório. Ele permite que as pessoas que chamam seu atendimento automático usem voz (reconhecimento de fala) ou suas respostas de teclado de telefone (DTMF) para inserir um nome completo ou parcial no diretório da empresa de pesquisa, localizar a pessoa e, em seguida, ter a chamada transferida para ela. Os usuários que você deseja ter localizado e alcançado usando Discagem por Nome não são necessários para ter um número de telefone ou ter Planos de Chamadas atribuídos a eles, mas eles devem ter uma licença do Sistema de Telefonia se eles são usuários online ou Enterprise Voice habilitados para usuários do **Skype for Business Server.** A discagem por Nome poderá até mesmo encontrar e transferir chamadas para usuários do Microsoft Teams hospedados em diferentes países ou regiões para organizações multi-nacionais. Considerando os pré-requisitos envolvidos, você habilita explicitamente Dial by Name em um atendimento automático.

Discar por extensão é um recurso de um atendimento automático que também faz parte da pesquisa de diretório. Ele permite que as pessoas que chamam o seu atendimento automático usem voz (reconhecimento de fala) ou suas respostas de teclado de telefone (DTMF) para inserir a extensão de telefone do usuário que estão tentando alcançar e, em seguida, fazer com que a chamada seja transferida para eles. Os usuários que você deseja ter localizado e alcançado usando o Dial por extensão não são necessários para ter um número de telefone ou ter Planos de Chamadas atribuídos a eles, mas eles devem ter uma licença do Sistema de Telefonia se eles são usuários online ou Enterprise Voice habilitados para usuários do **Skype for Business Server.** Você também precisará ter um plano de discagem configurado adequadamente para seus usuários. A discagem por extensão poderá até mesmo encontrar e transferir chamadas para usuários do Microsoft Teams hospedados em diferentes países ou regiões para organizações multi-nacionais. Considerando os pré-requisitos envolvidos, você habilita explicitamente Dial por extensão em um atendimento automático.

#### <a name="maximum-directory-size"></a>Tamanho máximo do diretório

Não há limite para o número de usuários do Active Directory Discar por Nome e Discar por Extensão pode dar suporte quando um chamador pesquisa por uma pessoa específica. Um chamador pode inserir nomes parciais ou completos (FirstName + LastName e também LastName + FirstName), mas precisa do número de extensão completo. O tamanho máximo da lista de nomes que um único atendimento automático pode suportar usando o reconhecimento de fala é de 80.000 usuários.
  
|Tipo de entrada|Formato de pesquisa|Número máximo de usuários em uma organização|
|:-----|:-----|:-----|
|DTMF (entrada de teclado) |Parcial  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome |Sem limite  |
|Fala (entrada de voz) |FirstName  <br/> LastName  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome  | 80.000 usuários |

> [!NOTE]
> Se você estiver usando Dial by Name com reconhecimento de fala, mas o Active Directory da sua organização for maior que 80.000 usuários e você não tiver limitado o escopo de Discagem por Nome usando o recurso Escopo de Discagem, Dial by Name ainda funcionará para seus chamadores usando um teclado de telefone e as entradas de voz estarão disponíveis para todos os outros cenários. Você pode usar o recurso Escopo de Discagem para restringir os nomes que são acessíveis mudando o escopo da Discagem por Nome para um atendedor automático específico.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Discar por Nome - entrada de teclado (DTMF)

As pessoas que estão ligando podem usar Dial by Name para chegar aos usuários especificando o nome completo ou parcial da pessoa que estão tentando alcançar. Há vários formatos que podem ser usados quando o nome é inserido.

Ao pesquisar o diretório de sua organização, as pessoas podem usar a tecla '0' (zero) para indicar um espaço entre o nome e o sobrenome ou sobrenome e nome. Quando eles estão inserindo o nome, eles serão solicitados a encerrar a entrada do teclado com a tecla #. Por exemplo, "Depois que você inserir o nome da pessoa que está tentando contatar, pressione #". Se vários nomes forem localizados, a pessoa que liga receberá uma lista de nomes para escolher.
  
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

#### <a name="dial-by-name---name-recognition-with-speech"></a>Discar por Nome - Reconhecimento de nome pela fala

As pessoas podem procurar outras pessoas em sua organização com sua voz (reconhecimento de fala). Eles também podem entrar em contato com qualquer pessoa no Active Directory dizendo o nome da pessoa que estão tentando localizar. O uso de entradas de voz pode reconhecer nomes em vários formatos, incluindo FirstName, LastName, FirstName + LastName ou LastName + FirstName.
  
Você pode habilitar o reconhecimento de fala para um atendimento automático, mas a entrada do teclado de telefone (DTMF) não está desabilitada. A entrada do teclado de telefone pode ser usada a qualquer momento, mesmo que o reconhecimento de fala seja habilitado no atendimento automático.
  
Assim como com a entrada do teclado de telefone, se vários nomes são encontrados, a pessoa que está chamando ouvir uma lista de nomes para selecionar.
  
Os chamadores podem dizer nomes nos seguintes formatos:
  
|Nome com fala|Tipo de pesquisa|Exemplo|Resultado de pesquisa|
|:-----|:-----|:-----|:-----|
|Nome + Sobrenome |Completo |Amos Marble |Amos Marble |
|Sobrenome + Nome |Completo  |Marble Amos |Amos Marble |
|FirstName |Completo |Amos |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Amos Jones |
|LastName |Completo |Marble |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Ben Marble |

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório para Discagem por Nome com reconhecimento de fala devido ao atraso de replicação do Active Directory.
  
### <a name="language-support"></a>Suporte a idiomas

Os idiomas a seguir estão disponíveis para texto em fala usado com prompts de saída:
  
|A-E|E-J|K-Z|
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

A entrada de reconhecimento de fala para os atendimentos automáticos está disponível nos seguintes idiomas:
  
|A-F|F-Z|
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

### <a name="the-operator-option"></a>A opção de operador

Opcionalmente, um atendente automático pode ser definido para dar a um chamador uma seleção para falar com um operador humano.
  
A tecla 0 e o comando de voz "Operator" direcionam a chamada para o operador designado por padrão. Esse é o caso de todos os idiomas com suporte para reconhecimento de fala. Você também pode usar **Set menu Options** para definir um valor personalizado para o Operador.
  
O operador pode ser definido como:
  
- Um usuário do Microsoft Teams ou um usuário do Skype for Business Server Enterprise Voice habilitado.
- Outro atendedor automático que é configurado para sua organização.
- Qualquer fila de chamada existente que é configurada em sua organização. Para ver mais sobre filas de chamada, consulte [Create a Cloud call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

### <a name="business-hours-and-call-handling"></a>Horários comerciais e administração de chamada

O horário comercial pode ser definido em cada atendimento automático. Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão. O horário comercial pode ser definido com pausas no tempo durante o dia e todas as horas que não estão definidas como horário comercial são consideradas após o horário. Você pode definir diferentes opções de tratamento de chamadas de entrada e saudações diferentes (que são opcionais) para horário comercial e pós-horário.
  
Cada atendimento automático tem várias opções possíveis de tratamento de chamada:
  
- A chamada pode ser desconectada depois que uma saudação é reproduzida.
- Também é possível:
  - Redirecione a chamada para um  usuário do Microsoft Teams que tenha uma licença do Sistema de Telefonia Enterprise Voice habilitada ou tenha Planos de Chamadas atribuídos a eles. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para isso, selecione uma **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal.

  - Redirecionar a chamada para uma fila de chamada. Para ver mais sobre filas de chamada, consulte [Create a Cloud call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

  - Redirecione a chamada para outro atendimento automático.

Essas opções são expressas ao chamador pelo atendimento automático quando ele reproduz prompts de menu. Por exemplo: "Pressione 1 para Vendas, Pressione 2 para Serviços. Para falar com o operador, pressione 0 a qualquer momento."

### <a name="set-menu-options"></a>Definir opções de menu

Os atendentes automáticos de nuvem permitem que você crie prompts de menu ("Pressione 1 para Vendas, Pressione 2 para Serviços") e configurar opções de menu para rotear chamadas com base em seleções de usuário. As opções de menu para um atendimento automático permitem que uma organização forneça uma série de opções que orientam os chamadores para seu destino mais rapidamente, sem depender de um operador humano para lidar com chamadas de entrada. Os prompts de menu podem ser criados usando texto para fala (prompts gerados pelo sistema) ou carregando um arquivo de áudio gravado. O reconhecimento de fala aceita comandos de voz para navegação sem mãos, mas as pessoas que estão ligando também podem usar o teclado do telefone para navegar nos menus.
  
As teclas de 0 a 9 podem ser atribuídas para discar chaves em um atendimento automático usando o Centro de administração do Skype for Business. Diferentes conjuntos de opções de menu podem ser criadas para os horários comerciais e horários fora do expediente, e você pode habilitar ou desabilitar o Discar por Nome nas **Opções de Menu**. As teclas podem ser mapeadas para transferir as chamadas para:
  
- Um operador, que é mapeado para a tecla 0 por padrão. No entanto, ele pode ser reatribuido para qualquer outra chave ou removido do menu.
- Uma fila de chamada.
- Outro atendedor automático. Os menus de vários níveis podem ser definidos apontando uma Opção de **Menu** em um atendimento automático para outro, com seu próprio conjunto de Opções de Menu, que é chamado de atendimento automático "aninhado".
- Um usuário do Microsoft Teams que tem uma licença **do** Sistema de Telefonia Enterprise Voice habilitada ou tem Planos de Chamadas atribuídos a eles. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para isso, selecione uma **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal.
  
O nome de cada opção de menu se tornará uma palavra-chave de reconhecimento de fala se o reconhecimento de fala tiver sido habilitado. Por exemplo, os chamadores podem dizer "Um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "Vendas" para selecionar a mesma opção de menu chamada "Vendas".
  
Para configurar um atendimento automático e as opções de menu, vá [Configurar um atendimento automático na nuvem.](create-a-phone-system-auto-attendant.md)
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Atribuindo números de telefone para um atendimento automático

Você pode atribuir um número de serviço da Microsoft, um número de roteamento direto ou um número híbrido à conta de recurso vinculada do seu assistente automático (ou a várias contas de recurso se mais de um número de telefone for desejado). Consulte [Plan Direct Routing](direct-routing-plan.md) para obter detalhes adicionais.

Para atribuir um número de serviço, você precisará obter ou portuar seus números de serviço de tarifação ou de tarifa gratuita existentes. Depois que você receber os números de telefone de serviço gratuito ou de chamada gratuita, eles aparecerão no Centro de administração do **Skype for Business** números de telefone de  >    >  **voz.** **Tipo de** número listado como **Serviço - Gratuito**. Para obter seus números de serviço, consulte Obter números de telefone de serviço para [o Skype for Business](./getting-service-phone-numbers.md) e o Microsoft Teams ou, se você quiser transferir e o número de serviço existente, consulte Transfer phone numbers to [Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, não poderá usar o Centro de administração do Microsoft Teams para obter números de serviço. Vá [Gerenciar números de telefone para sua organização,](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez disso, para ver como fazer isso.
  
## <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](./getting-service-phone-numbers.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)