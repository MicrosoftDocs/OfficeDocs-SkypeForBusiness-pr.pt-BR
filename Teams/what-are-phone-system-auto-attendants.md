---
title: Cite atendedores automáticos de nuvem.
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.autoattendants.overview
ms.custom:
- Phone System
description: Saiba quais são os atendedores automáticos de nuvem e como usá-los.
ms.openlocfilehash: 99310e44fbab43e16d0816acdb8a85815863b286
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211689"
---
# <a name="what-are-cloud-auto-attendants"></a>Cite atendedores automáticos de nuvem.

Sistema telefônico no Office 365 fornece atendedores automáticos, que podem ser usados para permitir que externo e internos chamadores mover através de um sistema de menu localizar e colocar ou transferir chamadas para usuários da empresa ou departamentos na organização.
  
Um atendedor automático é uma série de prompts de voz ou arquivos de áudio que os chamadores ouvem, em vez de um operador humano quando ele liga uma organização. Quando as pessoas chamam um número associado a um atendedor automático, suas escolhas podem redirecionar a chamada para um usuário ou localizar alguém em sua organização e conecte-se a esse usuário. Eles podem express suas escolhas e interagir com o sistema de menus usando um teclado numérico do telefone (DTMF) ou o reconhecimento de fala.
  
Para configurar um atendedor automático para o sistema telefônico no Office 365, vá para [Configurar um atendedor automático de nuvem](create-a-phone-system-auto-attendant.md).
  
Um atendedor automático da nuvem tem os seguintes recursos:
  
- Ele oferece saudações corporativas ou informativas.
- Ele oferece menus corporativos personalizados. Você pode personalizar esses menus para ter mais do que um nível.
- Ele fornece pesquisa de diretório que permite que as pessoas que ligam para pesquisar o diretório da organização para um nome.
- Ele permite que uma pessoa que chama para alcançar ou deixar uma mensagem para uma pessoa em sua organização.
- Suporte a vários idiomas para prompts de texto em fala e reconhecimento de fala.
- Suporte a especificação de feriados e horário comercial.
- Suporte a transferir chamada para um operador, outros usuários, filas de chamada e atendedores automáticos.

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e Skype para Business Online.

## <a name="getting-started"></a>Introdução

Para começar a usar os atendedores automáticos, é importante lembrar-se de que:

- Um atendedor automático é necessário ter uma conta de recurso associado. Consulte [Gerenciar contas de recursos em equipes](manage-resource-accounts.md) para obter detalhes sobre as contas de recursos.
- Se você planeja atribua um número de roteamento direto, você precisará adquirir e atribuir as seguintes licenças às suas contas de recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico\).
- Se você estiver atribuindo um número de serviço da Microsoft em vez disso, você precisará adquirir e atribuir as seguintes licenças à sua conta do recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico e um plano de chamar\).
- Você só precisa licenciar as contas de recursos com um número de telefone atribuído a eles. Em uma fila de chamada e atendente automático aninhados, você não precisará licenciar o restante dos atendedores automáticos ou chamada filas se eles não tiverem números de telefone associados a eles. 

> [!NOTE]
> Diretos números de serviço de roteamento para atendedor automático e filas de chamada são suportadas para os usuários de Teams da Microsoft e operadores somente no momento.

> [!NOTE]
> Microsoft está trabalhando em um modelo de licenciamento apropriado para aplicativos como atendedores automáticos de nuvem e filas de chamada, para agora você precisa usar o modelo de licenciamento por usuário.
    
   > [!TIP]
   > Para redirecionar chamadas para um operador ou uma opção de menu que é um usuário Online com uma licença de **Sistema telefônico** , você precisará habilitá-los para o Enterprise Voice ou atribuir chamar planos para acessá-los. Consulte [as equipes da Microsoft atribuir licenças](assign-teams-licenses.md). Você também pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obter e usar números gratuitos de serviço para seus atendedores automáticos, você precisará configurar créditos de comunicações. Para fazer isso, consulte [Cite Communications créditos?](what-are-communications-credits.md) e [Configurar créditos de comunicações para sua organização](set-up-communications-credits-for-your-organization.md).

    > [!IMPORTANT]
    > [!IMPORTANTE] Os números de telefone (assinante) não podem ser atribuídos aos atendedores automáticos  somente números de telefone de serviço chamadas gratuitas ou tarifadas podem ser usados.

- Um sistema de atendedor automático completa geralmente envolverá atendedores automáticos de vários e somente pode exigir um número de telefone atribuído único para o automático de nível superior ou entrada attendant. Outros atendedores automáticos ou filas de chamada no sistema completa somente serão necessário um número de telefone se você deseja fornecer vários pontos de entrada para o sistema.
- É possível aplicar mais de um número de telefone a um atendedor automático associando mais de uma conta de recurso para um atendedor automático.
  
## <a name="feature-overview"></a>Visão geral do recurso

### <a name="dial-by-name"></a>Discar por Nome

Discagem pelo nome, é um recurso de um atendedor automático que também é conhecida como a pesquisa de diretório. Ele permite que as pessoas que chamar o atendedor automático para usar voz (reconhecimento de fala) ou suas respostas de teclado (DTMF) do telefone para inserir um nome completo ou parcial para pesquisar o diretório da empresa, localizar a pessoa e, em seguida, tem transferir a chamada para eles. Usuários que deverão ter localizado e alcançado utilizando discagem por nome **não é necessário tiverem um número de telefone ou chamar planos atribuiu a eles, mas eles devem ter uma licença de sistema telefônico se eles são usuários online ou EV habilitado para onpremises usuários**. Discagem por nome ainda poderão localizar e transferir chamadas para usuários hospedados em diferentes países ou regiões para organizações multinacionais Teams da Microsoft.

### <a name="maximum-directory-size"></a>Tamanho máximo do diretório

Não há nenhum limite do tamanho do Active Directory para o qual a discagem por nome é suportada ao usar o teclado do telefone a ser pesquisado para digitar nomes parciais ou completos (FirstName + LastName e também LastName + FirstName). No entanto, o tamanho máximo do nome da lista que um atendedor automático único pode dar suporte usando o reconhecimento de nome com fala é 80.000 usuários.
  
|Tipo de entrada|Formato de pesquisa|Número máximo de usuários em uma organização|
|:-----|:-----|:-----|
|DTMF (entrada de teclado) |Parcial  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome |Sem limite  |
|Fala (entrada de voz) |FirstName  <br/> LastName  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome  | 80.000 usuários |

> [!NOTE]
> Se você estiver usando a discagem pelo nome, com a fala reconhecimento, mas o Active Directory da sua organização for maior do que 80.000 usuários e você ainda não limitados o escopo da discagem por nome usando o recurso de escopo de discagem, a discagem por nome funcionará para os chamadores usando um teclado do telefone , e entradas de voz estarão disponíveis para todos os outros cenários. Você pode usar o recurso Escopo de Discagem para restringir os nomes que são acessíveis mudando o escopo da Discagem por Nome para um atendedor automático específico.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Discar por Nome - entrada de teclado (DTMF)

Pessoas chamando em podem usar discagem pelo nome, para atingir usuários especificando-se tanto o nome completo ou parcial da pessoa que estão tentando fazer contato. Há vários formatos que podem ser usados quando o nome é inserido.

Ao pesquisar o diretório de sua organização, as pessoas podem usar a tecla '0' (zero) para indicar um espaço entre o nome e o sobrenome ou sobrenome e nome. Quando eles estiver inserindo o nome, eles serão solicitados para encerrar seu entrada de teclado com a tecla #. Por exemplo, "Depois que você inserir o nome da pessoa que está tentando contatar, pressione #". Se vários nomes forem localizados, a pessoa que liga receberá uma lista de nomes para escolher.
  
As pessoas podem pesquisar os nomes em sua organização usando os seguintes formatos de pesquisa em seu teclado de telefone:
  
|Formato de nome|Tipo de pesquisa|Exemplo|Resultado de pesquisa|
|:-----|:-----|:-----|:-----|
|Nome + Sobrenome |Completo  |Amos0Marble# |Amos Marble |
|Sobrenome + Nome |Completo |Marble0Amos#  |Amos Marble |
|FirstName  |Completo   |Amos#   |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |
|LastName |Completo |Marble#  |Pressione 1 para Amos Marble  <br/> Pressione 2 para Mary Marble |
|Nome ou Sobrenome |Parcial |Mar# |Pressione 1 para Mary Marble  <br/> Pressione 2 para Mary Jones  <br/> Pressione 3 para Amos Marcus |
|Nome + Sobrenome |Parcial |Mar0Amos# |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |
|Sobrenome + Nome |Parcial |Mar0Am# |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |

Há vários caracteres especiais que são usados durante a pesquisa de pessoas por meio de um teclado de telefone. Por exemplo, a pessoa será solicitada a usar a tecla de cerquilha (#), enquanto a tecla zero (0) é usada para um espaço entre os nomes. Pressionar a tecla asterisco (*) repetirá a lista de nomes correspondentes para a pessoa.
  
|Caractere de teclado de telefone especial|O que significa|
|:-----|:-----|
|#   |Caractere final ao inserir um nome. |
|0   |Espaço entre nomes. |
|*    |Repetir a lista de nomes correspondentes. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Discar por Nome - Reconhecimento de nome pela fala

Pessoas podem pesquisar para outras pessoas em sua organização usando sua voz (reconhecimento de fala). Eles também podem alcançar qualquer pessoa Active Directory da empresa dizendo o nome da pessoa que estão tentando localizar. Usar as entradas de voz pode reconhecer nomes em vários formatos, incluindo FirstName, LastName, FirstName + LastName, ou LastName + FirstName.
  
Quando você habilita o reconhecimento de fala para um atendedor automático, entrada de teclado do telefone (DTMF) não será desabilitada para que ambos os tipos de entrada que possam ser usados. Entrada de teclado do telefone não pode ser desabilitada e pode ser usada a qualquer momento, mesmo se o reconhecimento de fala estiver habilitado no atendedor automático.
  
Como com a entrada de teclado de telefone, se vários nomes forem localizados, a pessoa que liga receberá uma lista de nomes para escolher.
  
As pessoas que ligarem poderão falar os nomes nos seguintes formatos:
  
|Nomeie com a fala|Tipo de pesquisa|Exemplo|Resultado de pesquisa|
|:-----|:-----|:-----|:-----|
|Nome + Sobrenome |Completo |Amos Marble |Amos Marble |
|Sobrenome + Nome |Completo  |Marble Amos |Amos Marble |
|FirstName |Completo |Amos |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Amos Jones |
|LastName |Completo |Marble |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Ben Marble |

> [!NOTE]
> Poderá demorar até 36 horas para um novo usuário ter seu nome listado no diretório para discagem por nome com reconhecimento de fala devido à latência de replicação do Active Directory.
  
### <a name="language-support"></a>Idioma de suporte

Os seguintes idiomas estão disponíveis para conversão de texto em fala:
  
||||
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

O reconhecimento de fala para atendedores automáticos está disponível nos seguintes idiomas:
  
|||
|:-----|:-----|
|Chinês (ZH)  |Francês (FR)  |
|Inglês (AU)  |Alemão (DE)  |
|Inglês (CA)  |Italiano (IT)  |
|Inglês (IN)  |Japonês (JP)  |
|Inglês (Reino Unido)  |Português (BR)  |
|Inglês (EUA)  |Espanhol (ES)  |
|Francês (CA)   |Espanhol (MX)  |

Os seguintes comandos de voz estão disponíveis nos quatorze (14) idiomas aceitos para reconhecimento e fala:
  
|Comando de voz| Corresponde à |
|:-----|:-----|
|Sim |Sim - corresponde ao pressionamento 1 para Sim. |
|Não |Não corresponde ao pressionamento 2 para Não |
|Repetir |Repete a lista de opções - corresponde a pressionar * repetir a lista de opções. |
|Operador |Sessão de grupo para operador - corresponde a pressionar 0 para "Operador". |
|Menu Principal  |Leva o chamador para o menu principal do atendedor automático. |
|Zero |Corresponde a pressionar 0 (por padrão, o mesmo que "Operador").|
|Um |Corresponde a pressionar 1. |
|Dois |Corresponde a pressionar 2. |
|Três|Corresponde a pressionar 3.|
|Quatro |Corresponde a pressionar 4. |
|Cinco |Corresponde a pressionar 5. |
|Seis  |Corresponde a pressionar 6. |
|Sete |Corresponde a pressionar 7.|
|Oito |Corresponde a pressionar 8.|
|Nove  |Corresponde a pressionar 9.|

### <a name="using-the-operator-option"></a>Usando a opção do operador

Usando o operador de um atendedor automático é uma configuração opcional que fornece o chamador com uma opção para falar com um operador humano.
  
Chave 0 e o comando de voz "Operador" direcionam a chamada ao operador designado por padrão. Esse é o caso para todos os idiomas com suporte para reconhecimento de fala. Você também pode usar as **Opções de Menu** para definir um valor personalizado para o operador.
  
O operador pode ser definido como:
  
- Um usuário do Microsoft Teams ou um Skype for Business no usuário local que esteja habilitado para Enterprise Voice.
  
- Outro atendedor automático que é configurado para sua organização.
- Qualquer fila de chamada existente que é configurada em sua organização. Para obter mais informações sobre filas de espera de chamada, consulte [criar uma fila de chamada de nuvem](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

### <a name="business-hours-and-call-handling"></a>Horários comerciais e administração de chamada

Os horários comerciais são definidos em cada atendedor automático. Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão. Horário comercial podem ser definido com quebras em tempo durante o dia e todos os horários que não são definidos como horários comerciais são considerados fora do horário comercial. Você pode definir diferentes opções de atendimento de chamadas recebidas e saudações diferentes (que são opcionais), e ambas podem ser definidas para horário comercial e fora do horário comercial.
  
Cada atendedor automático tem opções de atendimento de chamadas que podem ser definidas:
  
- Você pode ter a chamada desconectada logo após a saudação.
- Também é possível:
  - Redirecionar a chamada para um usuário de Teams da Microsoft que tem uma licença de **Sistema telefônico** que esteja habilitado para Enterprise Voice ou chamar planos atribuiu a eles. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para isso, selecione uma **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal.

  
  - Redirecione a chamada para uma fila de espera de chamada. Para obter mais informações sobre filas de espera de chamada, consulte [criar uma fila de chamada de nuvem](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

  - Redirecione a chamada para outro atendedor automático que você definiu.
- Criar opções de menu e reproduzir o prompt do menu para o chamador. Por exemplo: "Pressione 1 para Vendas, Pressione 2 para Serviços. Para falar com o operador, pressione 0 a qualquer momento."

### <a name="menu-options"></a>Opções do menu

Atendedores automáticos de nuvem permitem que você crie os prompts de menu ("Pressione 1 para vendas, pressione 2 para serviços") e defina as opções de menu para rotear chamadas com base em que o usuário seleciona. A configuração das opções de menu de um atendedor automático permite que uma organização forneça orientação interativa para levar a pessoa a seu destino mais rápido, sem contar com um operador humano para administrar as chamadas de entrada. Os prompts de menu podem ser criados usando texto em fala (gerada pelo sistema prompts) ou carregando um arquivo de áudio que foi registrado. O reconhecimento de fala usa comandos de voz para navegação sem usar as mãos, mas os chamadores também podem usar o teclado do telefone para navegar pelos menus.
  
Teclas 0 a 9 podem ser atribuídas às **Opções de Menu** em um atendedor automático usando o Skype para o Centro de administração de negócios. Diferentes conjuntos de opções de menu podem ser criadas para os horários comerciais e horários fora do expediente, e você pode habilitar ou desabilitar o Discar por Nome nas **Opções de Menu**. As teclas podem ser mapeadas para transferir as chamadas para:
  
- Um operador, que é mapeado para a tecla 0 por padrão. No entanto, ele pode ser novamente atribuído a qualquer outra tecla, ou removido do menu.
- Uma fila de espera de chamada.
- Outro atendedor automático. Menus de vários níveis podem ser configuradas pelo apontando uma **Opção de Menu** no atendedor automático de um para o outro atendedor com seu próprio conjunto de opções de Menu, que é chamado um atendedor automático "aninhados".
- Um usuário do Microsoft Teams que tem um **Sistema telefônico** licenciar que esteja habilitado para Enterprise Voice ou chamar planos atribuiu a eles. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para isso, selecione uma **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal.
  
O nome de cada opção de menu torna-se uma palavra-chave de reconhecimento de fala, se tiver sido habilitado o reconhecimento de fala. Por exemplo, os chamadores podem dizer "One" para selecionar a opção de menu mapeada para a tecla 1 ou simplesmente dizem "Sales" para selecionar a opção de menu mesmo chamada "Sales".
  
Para configurar um atendedor automático e as opções de menu, vá [Configurar um atendedor automático de nuvem](create-a-phone-system-auto-attendant.md).
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Atribuindo números de telefone para um atendedor automático

Você pode atribuir um Microsoft chamar o número de plano de serviço ou um número de híbrido de roteamento direto para o atendedor automático. Para obter detalhes, consulte [Planejar roteamento direto](direct-routing-plan.md) .

Para atribuir um número de serviço, você precisará obter ou transferir sua chamada Tarifada existente ou serviço gratuito números. Depois que você fazer a chamada Tarifada ou números de telefone gratuitos de serviço, eles serão exibidos no <!-- validate nav path --> **Skype para centro de administração de negócios** > **voz** > **números de telefone**e a disposição de **tipo de número** listado listada como **serviço - gratuito**. Para obter seus números de serviço, consulte [Getting números de telefone de serviço para Skype para equipes da Microsoft e de negócios](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) ou se você deseja transferir e o número de serviço existente, consulte [transferir os números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, você não pode usar o Centro de administração do Microsoft Teams para obter os números de serviço. Vá [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez disso, para ver como fazê-lo.
  
## <a name="related-topics"></a>Tópicos relacionados

[Veja aqui o que você obtém com o Sistema de Telefonia no Office 365](here-s-what-you-get-with-phone-system.md)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Exemplo de pequenas empresas - Configurar um atendedor automático](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)
