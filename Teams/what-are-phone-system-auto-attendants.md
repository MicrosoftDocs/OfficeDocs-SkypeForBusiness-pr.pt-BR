---
title: O que são os participantes automáticos da nuvem?
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
description: Saiba mais sobre os participantes automáticos da nuvem e como usá-los para permitir que os chamadores se movam por um sistema de menus para localizar e fazer ou transferir chamadas para usuários ou departamentos.
ms.openlocfilehash: 862272ffe0cb42edc092c513823f421ab1c5bd95
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918937"
---
# <a name="what-are-cloud-auto-attendants"></a>O que são os participantes automáticos da nuvem?

O Sistema telefônico fornece os atenderes automáticos, que podem ser usados para permitir que os chamadores externos e internos se movam por um sistema de menus para localizar e fazer ou transferir chamadas para usuários ou departamentos em sua organização.
  
Um assistente automático geralmente é um nó em um sistema, dando a um chamador uma série de prompts de voz ou arquivos de áudio que eles ouvem em vez de um operador humano. Quando as pessoas ligam para um número associado a um assistente automático, suas escolhas podem redirecionar a chamada para um usuário ou localizar alguém em sua organização e se conectar a esse usuário. Eles podem expressar suas escolhas e interagir com o sistema de menus usando um teclado de telefone (DTMF) ou reconhecimento de fala. As opções que elas fazem também podem redirecionar a chamada para outro atendimento automático ou para uma fila de chamada.
  
Para configurar um atender automático para o Sistema de Telefonia, vá [para Configurar um atender automático na nuvem.](create-a-phone-system-auto-attendant.md)
  
Um assistente automático na nuvem tem os seguintes recursos:
  
- Ele oferece saudações corporativas ou informativas.
- Ele oferece menus corporativos personalizados. Você pode personalizar esses menus para ter mais do que um nível.
- Ele fornece uma pesquisa de diretório que permite que as pessoas que ligarem pesquisem um nome no diretório da organização.
- Ele permite que alguém que liga para entrar em contato ou deixar uma mensagem para uma pessoa em sua organização.
- Ele oferece suporte a vários idiomas para solicitações, texto em fala e reconhecimento de fala.
- Ele dá suporte à especificação de feriados e horários comerciais.
- Ele dá suporte à transferência de chamada para um operador, outros usuários, filas de chamada e atendedores automáticos.
- Ele dá suporte à caixa postal compartilhada para que os chamadores deixem uma mensagem para uma organização.

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e ao Skype for Business Online.

## <a name="getting-started"></a>Introdução

Para começar a usar os atendedores automáticos, é importante lembrar-se de que:

- Um assistente automático é necessário para ter uma conta de recurso associada. Consulte [Gerenciar contas de recursos no Teams para](manage-resource-accounts.md) obter detalhes sobre contas de recursos. <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- Ao atribuir um número de telefone a um atender automático, estritamente falando, você o está atribuindo à conta de recurso associada a esse atender automático. Isso fornece uma maneira de ter mais de um número de telefone acessando um atender automático. Na maioria das vezes, uma conta de recurso usará a licença de Usuário Virtual do Sistema De Telefonia sem custo. Esta licença fornece recursos do Sistema telefônico para números de telefone no nível organizacional e permite que você crie atendimentos automáticos e filas de chamadas.

> [!NOTE]
> Os números de serviço de Roteamento Direto para o atendimento automático e filas de chamadas são suportados somente para usuários e agentes de chamada do Microsoft Teams.

   > [!TIP]
   > Para redirecionar chamadas para um operador ou uma  opção de menu que seja um usuário online com uma licença do Sistema de Telefonia, você precisará habilitar a conta dele para o Enterprise Voice ou atribuir Planos de Chamada a ele. Consulte Atribuir licenças de [complemento do Microsoft Teams.](teams-add-on-licensing/assign-teams-add-on-licenses.md) Você também pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obter e usar números de serviço de tarifa gratuita para os seus atendimentos automáticos, você precisa configurar Créditos de Comunicação. Para fazer isso, veja [O que são Créditos de Comunicação?](what-are-communications-credits.md) [e Configurar Créditos de Comunicação para sua organização.](set-up-communications-credits-for-your-organization.md)

    > [!IMPORTANT]
    > [!IMPORTANTE] Os números de telefone (assinante) não podem ser atribuídos aos atendedores automáticos  somente números de telefone de serviço chamadas gratuitas ou tarifadas podem ser usados.

- Um sistema de atendimento automático completo normalmente envolverá vários participantes automáticos.
- É possível aplicar mais de um número de telefone aos atenderes automáticos de nível de entrada.
- Os atenderes automáticos de nível de não entrada ou filas de chamadas no sistema completo só precisarão de um número de telefone se eles realizarem chamadas PSTN de saída.
  
## <a name="feature-overview"></a>Visão geral do recurso

### <a name="searching-for-users"></a>Pesquisando usuários

Discar por Nome é um recurso de um assistente automático que também é conhecido como pesquisa de diretório. Ele permite que as pessoas que liguem para o seu atender automático usem as respostas de voz (reconhecimento de fala) ou do teclado de telefone (DTMF) para inserir um nome completo ou parcial para pesquisar o diretório da empresa, localizar a pessoa e, em seguida, transferir a chamada para ela. Os usuários que você deseja localizar e acessar usando o Discar por Nome não são obrigados a ter um número de telefone ou ter Planos de Chamada atribuídos a eles, mas eles devem ter uma licença do Sistema de Telefonia se são usuários online ou o Enterprise Voice habilitado para usuários do **Skype for Business Server.** O discar por Nome ainda poderá encontrar e transferir chamadas para usuários do Microsoft Teams hospedados em diferentes países ou regiões para organizações multinacionais. De acordo com os pré-requisitos envolvidos, você habilita explicitamente o Discar por Nome em um atendimento automático.

Discar por extensão é um recurso de um assistente automático que também faz parte da pesquisa de diretório. Ele permite que as pessoas que liguem para o seu atender automático usem respostas de voz (reconhecimento de fala) ou do teclado de telefone (DTMF) para inserirem a extensão de telefone do usuário que estão tentando contabilitar e, em seguida, transferirem a chamada para eles. Os usuários que você deseja localizar e acessar usando o Discar por extensão não são necessários para ter um número de telefone ou ter Planos de Chamada atribuídos a eles, mas eles devem ter uma licença do Sistema de Telefonia se são usuários online ou o Enterprise Voice habilitado para usuários do **Skype for Business Server.** Você também precisará ter um plano de discagem configurado adequadamente para seus usuários. O discar por extensão ainda poderá encontrar e transferir chamadas para usuários do Microsoft Teams hospedados em diferentes países ou regiões para organizações multinacionais. Considerando os pré-requisitos envolvidos, você habilita explicitamente o Discar por extensão em um atendimento automático.

#### <a name="maximum-directory-size"></a>Tamanho máximo do diretório

Não há limite para o número de usuários do Active Directory Discar por Nome e Discar por Extensão pode ser suportado quando um chamador procura uma pessoa específica. Um chamador pode inserir nomes parciais ou completos (Nome + Sobrenome e também Sobrenome + Nome), mas precisa do número completo da extensão. O tamanho máximo da lista de nomes que um único assistente automático pode dar suporte usando o reconhecimento de fala é de 80.000 usuários.
  
|Tipo de entrada|Formato de pesquisa|Número máximo de usuários em uma organização|
|:-----|:-----|:-----|
|DTMF (entrada de teclado) |Parcial  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome |Sem limite  |
|Fala (entrada de voz) |Firstname  <br/> Lastname  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome  | 80.000 usuários |

> [!NOTE]
> Se você estiver usando Discar por Nome com reconhecimento de fala, mas o Active Directory da sua organização for maior que 80.000 usuários e você não tiver limitado o escopo de Discar por Nome usando o recurso Escopo de Discagem, Discar por Nome ainda funcionará para os chamadores usando um teclado de telefone e as entradas de voz estarão disponíveis para todos os outros cenários. Você pode usar o recurso Escopo de Discagem para restringir os nomes que são acessíveis mudando o escopo da Discagem por Nome para um atendedor automático específico.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Discar por Nome - entrada de teclado (DTMF)

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

#### <a name="dial-by-name---name-recognition-with-speech"></a>Discar por Nome - Reconhecimento de nome pela fala

As pessoas podem procurar outras pessoas em sua organização com voz (reconhecimento de fala). Eles também podem entrar em contato com qualquer pessoa no Active Directory dizendo o nome da pessoa que estão tentando localizar. O uso de entradas de voz pode reconhecer nomes em vários formatos, incluindo Nome, Sobrenome, Nome + Sobrenome ou Sobrenome + Nome.
  
Você pode habilitar o reconhecimento de fala para um atender automático, mas a entrada do teclado de telefone (DTMF) não está desabilitada. A entrada do teclado de telefone pode ser usada a qualquer momento, mesmo que o reconhecimento de fala seja habilitado no atender automaticamente.
  
Como na entrada do teclado do telefone, se vários nomes são encontrados, a pessoa que liga ouve uma lista de nomes para selecionar.
  
Os chamadores podem dizer nomes nos seguintes formatos:
  
|Nome com fala|Tipo de pesquisa|Exemplo|Resultado de pesquisa|
|:-----|:-----|:-----|:-----|
|Nome + Sobrenome |Completo |Amos Marble |Amos Marble |
|Sobrenome + Nome |Completo  |Marble Amos |Amos Marble |
|Firstname |Completo |Amos |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Amos Jones |
|Lastname |Completo |Marble |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Ben Marble |

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório para Discar por Nome com reconhecimento de fala devido ao atraso de replicação do Active Directory.
  
### <a name="language-support"></a>Suporte a idiomas

Os seguintes idiomas estão disponíveis para texto em fala usados com prompts de saída:
  
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

A entrada de reconhecimento de fala para os participantes automáticos está disponível nos seguintes idiomas:
  
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

### <a name="the-operator-option"></a>A opção do operador

Opcionalmente, um assistente automático pode ser definido para dar a um chamador uma seleção para falar com um operador humano.
  
A tecla 0 e o comando de voz "Operador" direcionam a chamada para o operador designado por padrão. Esse é o caso para todos os idiomas com suporte para reconhecimento de fala. Você também pode usar **Definir opções de menu** para definir um valor personalizado para o Operador.
  
O operador pode ser definido como:
  
- Um usuário do Microsoft Teams ou um usuário do Skype for Business Server habilitado para o Enterprise Voice.
- Outro atendedor automático que é configurado para sua organização.
- Qualquer fila de chamada existente que é configurada em sua organização. Para ver mais sobre filas de chamada, consulte [Criar uma fila de chamada na nuvem.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

### <a name="business-hours-and-call-handling"></a>Horários comerciais e administração de chamada

Os horários comerciais podem ser definidos em cada atendimento automático. Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão. Os horários comerciais podem ser definidos com quebras de tempo durante o dia, e todas as horas que não são definidas como horários comerciais são consideradas horas extras. Você pode definir diferentes opções de administração de chamadas de entrada e saudações diferentes (que são opcionais) para horários comerciais e horas extras.
  
Cada atender automático tem várias opções possíveis de tratamento de chamada:
  
- A chamada pode ser desconectada depois que uma saudação é reproduzda.
- Também é possível:
  - Redirecione a chamada para um  usuário do Microsoft Teams que tenha uma licença do Sistema de Telefonia que está habilitada para o Enterprise Voice ou que tenha Planos de Chamada atribuídos a ele. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para isso, selecione uma **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal.

  - Redirecionar a chamada para uma fila de chamada. Para ver mais sobre filas de chamada, consulte [Criar uma fila de chamada na nuvem.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

  - Redirecionar a chamada para outro atendimento automático.

Essas opções são expressas ao chamador pelo atendimento automático quando ele reproduz prompts de menu. Por exemplo: "Pressione 1 para Vendas, Pressione 2 para Serviços. Para falar com o operador, pressione 0 a qualquer momento."

### <a name="set-menu-options"></a>Definir opções de menu

Os participantes automáticos da nuvem permitem que você crie prompts de menu ("Pressione 1 para Vendas, Pressione 2 para Serviços") e configurar opções de menu para rotear chamadas com base nas seleções do usuário. As opções de menu para um atender automático permitem que uma organização forneça uma série de opções que orientam os chamadores para seu destino mais rapidamente, sem depender de um operador humano para lidar com chamadas recebidas. Os prompts de menu podem ser criados usando texto em fala (prompts gerados pelo sistema) ou carregando um arquivo de áudio gravado. O reconhecimento de fala aceita comandos de voz para navegação com as mãos livres, mas as pessoas que estão ligando também podem usar o teclado do telefone para navegar pelos menus.
  
As teclas 0 a 9 podem ser atribuídas a teclas de discagem em um atendimento automático usando o Centro de administração do Skype for Business. Diferentes conjuntos de opções de menu podem ser criadas para os horários comerciais e horários fora do expediente, e você pode habilitar ou desabilitar o Discar por Nome nas **Opções de Menu**. As teclas podem ser mapeadas para transferir as chamadas para:
  
- Um operador, que é mapeado para a tecla 0 por padrão. No entanto, ele pode ser reatribuido a qualquer outra tecla ou removido do menu.
- Uma fila de chamada.
- Outro atendedor automático. Os menus de vários níveis podem ser definidos apontando uma Opção de **Menu** em um atendimento automático para outro, com seu próprio conjunto de Opções de Menu, que é chamado de "assistente automático aninhado".
- Um usuário do Microsoft Teams que tem uma licença **do** Sistema de Telefonia que está habilitada para o Enterprise Voice ou tem Planos de Chamada atribuídos a ele. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para isso, selecione uma **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal.
  
O nome de cada opção de menu se tornará uma palavra-chave de reconhecimento de fala se o reconhecimento de fala tiver sido habilitado. Por exemplo, os chamadores podem dizer "Um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "Vendas" para selecionar a mesma opção de menu chamada "Vendas".
  
Para configurar um assistente automático e as opções de menu, vá [Configurar um assistente automático na nuvem.](create-a-phone-system-auto-attendant.md)
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Atribuindo números de telefone para um atender automático

Você pode atribuir um número de serviço da Microsoft, um número de roteamento direto ou um número híbrido à conta de recurso vinculado do seu atender automático (ou a várias contas de recurso se mais de um número de telefone for desejado). Consulte [Planejar Roteamento Direto](direct-routing-plan.md) para obter detalhes adicionais.

Para atribuir um número de serviço, você precisará obter ou fazer a portabilidade dos números de serviço de tarifação ou de tarifa gratuita existentes. Depois que você receber os números de telefone de serviço de chamada tarifada ou gratuita, eles aparecerão nos números de telefone de voz do Centro de administração do **Skype for**  >    >  Business. **O tipo de** número está **listado como Serviço – Tarifa gratuita.** Para obter os números de serviço, consulte Como obter números de telefone de serviço do [Skype for Business](/microsoftteams/getting-service-phone-numbers) e do Microsoft Teams ou, se você quiser transferir e o número de serviço existente, consulte Transferir números de telefone para o [Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, não poderá usar o Centro de administração do Microsoft Teams para obter números de serviço. Em [vez disso, gerencie números de](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) telefone da sua organização para ver como fazê-lo.
  
## <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
