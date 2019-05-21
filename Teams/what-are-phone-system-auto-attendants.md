---
title: Quais são os atendedores automáticos do Cloud?
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.autoattendants.overview
ms.custom:
- Phone System
description: Saiba o que são atendedores automáticos da nuvem e como usá-los.
ms.openlocfilehash: 3dc96398cb2aa9ab3eafcc6e5d38ad2feb44b45b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299037"
---
# <a name="what-are-cloud-auto-attendants"></a>Quais são os atendedores automáticos do Cloud?

O sistema telefônico no Office 365 fornece atendedores automáticos, que podem ser usados para permitir que chamadores externos e internos se movimentem por meio de um sistema de menus para localizar e fazer ou transferir chamadas para usuários ou departamentos da empresa em sua organização.
  
Um atendedor automático é uma série de prompts de voz ou arquivos de áudio que os chamadores ouvem em vez de uma operadora humana quando eles chamam uma organização. Quando as pessoas chamam um número associado a um atendedor automático, suas opções podem redirecionar a chamada para um usuário ou localizar alguém em sua organização e, em seguida, se conectar a esse usuário. Elas podem expressar suas escolhas e interagir com o sistema de menus usando um teclado de telefone (DTMF) ou reconhecimento de fala.
  
Para configurar um atendedor automático para o sistema telefônico no Office 365, vá para [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md).
  
Um atendedor automático na nuvem tem os seguintes recursos:
  
- Ele oferece saudações corporativas ou informativas.
- Ele oferece menus corporativos personalizados. Você pode personalizar esses menus para ter mais do que um nível.
- Ele fornece pesquisa de diretório que permite que as pessoas liguem para pesquisar o diretório da organização em busca de um nome.
- Ele permite que alguém que ligue para alcançar ou deixar uma mensagem para uma pessoa em sua organização.
- Ele oferece suporte a vários idiomas para solicitações, conversão de texto em fala e reconhecimento de fala.
- Ele é compatível com a especificação de feriados e horários de trabalho.
- Ele permite a transferência de chamadas para um operador, outros usuários, filas de chamadas e atendedores automáticos.

> [!NOTE]
> Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.

## <a name="getting-started"></a>Introdução

Para começar a usar os atendedores automáticos, é importante lembrar-se de que:

- Um atendedor automático é necessário para ter uma conta de recurso associada. Consulte [gerenciar contas de recursos no Teams](manage-resource-accounts.md) para obter detalhes sobre contas de recursos.
- Se você planeja atribuir um número de roteamento direto, será necessário adquirir e atribuir as seguintes licenças às contas \(do recurso Office 365 Enterprise E1, E3 ou E5 com o complemento do sistema telefônico.\)
- Se estiver atribuindo um número de serviço da Microsoft, você precisará adquirir e atribuir as seguintes licenças à sua conta \(de recurso Office 365 Enterprise E1, E3 ou e5, com o complemento do sistema de telefonia e um plano\)de chamadas.
- Você só precisa licenciar as contas de recursos com um número de telefone atribuído a ela. Em um atendedor automático aninhado ou fila de chamadas, você não precisa licenciar o restante dos atendedores automáticos ou filas de chamadas se eles não tiverem números de telefone associados a eles. 

> [!NOTE]
> Os números do serviço de roteamento direto para atendedor automático e filas de chamadas são suportados somente para usuários e agentes do Microsoft Teams.

> [!NOTE]
> A Microsoft está trabalhando em um modelo de licenciamento sem custo para aplicativos como atendedores automáticos da nuvem e filas de chamadas, por ora, você precisa usar o modelo de licenciamento do usuário.
    
   > [!TIP]
   > Para redirecionar chamadas para um operador ou uma opção de menu que seja um usuário online com uma licença do **sistema de telefonia** , você precisará habilitá-las para o Enterprise Voice ou atribuir planos de chamada a elas. Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md). Você também pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obter e usar números de serviço de chamada gratuita para seus atendedores automáticos, você precisa configurar créditos de comunicações. Para fazer isso, confira [o que são créditos de comunicações?](what-are-communications-credits.md) e [Configure créditos de comunicações para sua organização](set-up-communications-credits-for-your-organization.md).

    > [!IMPORTANT]
    > [!IMPORTANTE] Os números de telefone (assinante) não podem ser atribuídos aos atendedores automáticos  somente números de telefone de serviço chamadas gratuitas ou tarifadas podem ser usados.

- Um sistema de atendedor automático completo geralmente envolve vários atendedores automáticos e só pode exigir um único número de telefone atribuído para o atendedor automático de nível superior ou de entrada. Outros atendedores automáticos ou filas de chamadas em todo o sistema precisarão apenas de um número de telefone, se você quiser fornecer vários pontos de entrada no sistema.
- É possível aplicar mais de um número de telefone a um atendedor automático associando mais de uma conta de recurso a um atendedor automático.
  
## <a name="feature-overview"></a>Visão geral do recurso

### <a name="dial-by-name"></a>Discar por Nome

Discar por nome é um recurso de um atendedor automático que também é conhecido como pesquisa de diretório. Ele permite que as pessoas que chamam seu atendedor automático usem voz (reconhecimento de fala) ou as respostas do teclado de telefone (DTMF) para inserir um nome completo ou parcial para pesquisar o diretório da empresa, localizar a pessoa e fazer com que a chamada seja transferida para ela. Os usuários que você quer localizar e alcançarem usando a discagem por nome **não devem ter um número de telefone ou ter planos de chamada atribuídos a eles, mas devem ter uma licença de sistema telefônico se eles forem usuários online ou EV habilitado para usuários**onmises. Discar por nome poderá, até mesmo, localizar e transferir chamadas para os usuários do Microsoft Teams que são hospedados em diferentes países ou regiões para organizações multinacionais.

### <a name="maximum-directory-size"></a>Tamanho máximo do diretório

Não há limite no tamanho do Active Directory para o qual o dial por nome tem suporte ao usar o teclado numérico do telefone para procurar por inserir nomes parciais ou completos (nome + sobrenome e também sobrenome + nome). No entanto, o tamanho da lista de nomes máximo que um único atendedor automático pode oferecer suporte usando o reconhecimento de nome com fala é de 80.000 usuários.
  
|Tipo de entrada|Formato de pesquisa|Número máximo de usuários em uma organização|
|:-----|:-----|:-----|
|DTMF (entrada de teclado) |Parcial  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome |Sem limite  |
|Fala (entrada de voz) |Nome  <br/> Apelido  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome  | usuários do 80.000 |

> [!NOTE]
> Se você estiver usando o recurso discar por nome com reconhecimento de fala, mas o Active Directory da sua organização for maior do que o 80.000 usuários e você não tiver limitado o escopo de discagem por nome usando o recurso de escopo de discagem, o recurso discar por nome ainda funcionará para seus chamadores usando um teclado de telefone , e as entradas de voz estarão disponíveis para todos os outros cenários. Você pode usar o recurso Escopo de Discagem para restringir os nomes que são acessíveis mudando o escopo da Discagem por Nome para um atendedor automático específico.
  
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
|Nome + Sobrenome |Parcial |Mar0Amos# |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |
|Sobrenome + Nome |Parcial |Mar0Am# |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus |

Há vários caracteres especiais que são usados durante a pesquisa de pessoas por meio de um teclado de telefone. Por exemplo, a pessoa será solicitada a usar a tecla sustenido (#), enquanto a tecla zero (0) é usada para um espaço entre os nomes. Pressionar a tecla asterisco (*) repetirá a lista de nomes correspondentes para a pessoa.
  
|Caractere de teclado de telefone especial|O que significa|
|:-----|:-----|
|#   |Caractere final ao inserir um nome. |
|0   |Espaço entre nomes. |
|*    |Repetir a lista de nomes correspondentes. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Discar por Nome - Reconhecimento de nome pela fala

As pessoas podem pesquisar por outras pessoas em sua organização usando a voz (reconhecimento de fala). Eles também podem acessar qualquer pessoa no Active Directory da empresa informando o nome da pessoa que ele está tentando localizar. Usar entradas de voz pode reconhecer nomes em vários formatos, incluindo FirstName, LastName, FirstName + LastName ou LastName + FirstName.
  
Quando você habilita o reconhecimento de fala para um atendedor automático, a entrada do teclado numérico do telefone (DTMF) não é desativada, portanto, os dois tipos de entrada podem ser usados. A entrada do teclado do telefone não pode ser desabilitada e pode ser usada a qualquer momento, mesmo se o reconhecimento de fala estiver habilitado no atendente automático.
  
Como com a entrada de teclado de telefone, se vários nomes forem localizados, a pessoa que liga receberá uma lista de nomes para escolher.
  
As pessoas que ligarem poderão falar os nomes nos seguintes formatos:
  
|Nome com fala|Tipo de pesquisa|Exemplo|Resultado de pesquisa|
|:-----|:-----|:-----|:-----|
|Nome + Sobrenome |Completo |Amos Marble |Amos Marble |
|Sobrenome + Nome |Completo  |Marble Amos |Amos Marble |
|Nome |Completo |Amos |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Amos Jones |
|Apelido |Completo |Marble |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Ben Marble |

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha o nome listado no diretório para discar por nome com reconhecimento de fala devido à defasagem de replicação do Active Directory.
  
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
  
|Comando de voz| Corresponde a |
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

Usar o operador para um atendedor automático é uma configuração opcional que fornece ao chamador uma opção para falar com uma operadora humana.
  
A chave 0 e o comando de voz "operador" direcionam a chamada para o operador designado por padrão. Esse é o caso de todos os idiomas com suporte para o reconhecimento de fala. Você também pode usar **as opções de menu** para definir um valor personalizado para o operador.
  
O operador pode ser definido como:
  
- Um usuário do Microsoft Teams ou um Skype for Business no usuário premissável compatível com o Enterprise Voice.
  
- Outro atendedor automático que é configurado para sua organização.
- Qualquer fila de chamada existente que é configurada em sua organização. Para ver mais sobre filas de chamadas, consulte [criar uma fila de chamadas na nuvem](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

### <a name="business-hours-and-call-handling"></a>Horários comerciais e administração de chamada

Os horários comerciais são definidos em cada atendedor automático. Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão. O horário comercial pode ser definido com quebras de horário durante o dia, e todas as horas que não estão definidas como horário comercial são consideradas após o expediente. Você pode definir diferentes opções de tratamento de chamadas e saudações diferentes (que são opcionais) e ambas podem ser definidas para horas comerciais e horas extras.
  
Cada atendedor automático tem opções de tratamento de chamadas que podem ser definidas:
  
- Você pode ter a chamada desconectada logo após a saudação.
- Também é possível:
  - Redirecionar a chamada para um usuário do Microsoft Teams que tenha uma licença do **sistema de telefonia** compatível com o Enterprise Voice ou um plano de chamadas atribuído a ele. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para isso, selecione uma **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal.

  
  - Redirecionar a chamada para uma fila de chamadas. Para ver mais sobre filas de chamadas, consulte [criar uma fila de chamadas na nuvem](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

  - Redirecione a chamada para outro atendedor automático que você configurou.
- Criar opções de menu e reproduzir o prompt do menu para o chamador. Por exemplo: "Pressione 1 para Vendas, Pressione 2 para Serviços. Para falar com o operador, pressione 0 a qualquer momento."

### <a name="menu-options"></a>Opções do menu

Os atendedores automáticos da nuvem permitem criar prompts de menu ("Pressione 1 para vendas, pressione 2 para serviços") e configure as opções do menu para direcionar as chamadas com base no que o usuário seleciona. A configuração das opções de menu de um atendedor automático permite que uma organização forneça orientação interativa para levar a pessoa a seu destino mais rápido, sem contar com um operador humano para administrar as chamadas de entrada. Os prompts de menu podem ser criados usando a conversão de texto em fala (prompts gerados pelo sistema) ou carregando um arquivo de áudio que tenha sido gravado. O reconhecimento de fala usa comandos de voz para navegação sem usar as mãos, mas os chamadores também podem usar o teclado do telefone para navegar pelos menus.
  
As teclas de 0 a 9 podem ser atribuídas às **Opções de menu** em um atendedor automático usando o centro de administração do Skype for Business. Diferentes conjuntos de opções de menu podem ser criadas para os horários comerciais e horários fora do expediente, e você pode habilitar ou desabilitar o Discar por Nome nas **Opções de Menu**. As teclas podem ser mapeadas para transferir as chamadas para:
  
- Um operador, que é mapeado para a tecla 0 por padrão. No entanto, ele pode ser atribuído novamente a qualquer outra chave ou removido do menu.
- Uma fila de chamadas.
- Outro atendedor automático. Os menus de vários níveis podem ser configurados apontando uma **opção de menu** em um atendedor automático para outro atendedor automático com seu próprio conjunto de opções de menu, que é chamado de atendedor automático "aninhado".
- Um usuário do Microsoft Teams que tem uma licença do **sistema de telefonia** compatível com o Enterprise Voice ou tem planos de chamada atribuídos. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para isso, selecione uma **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal.
  
O nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala se o reconhecimento de fala estiver habilitado. Por exemplo, os chamadores podem dizer "um" para selecionar a opção de menu mapeada para a tecla 1 ou podem simplesmente dizer "vendas" para selecionar a mesma opção de menu chamada "vendas".
  
Para configurar um atendedor automático e as opções de menu, vá [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md).
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Atribuindo números de telefone para um atendedor automático

Você pode atribuir um número de serviço do plano de chamadas da Microsoft ou um número híbrido de roteamento direto para o atendedor automático. Consulte [planejar o roteamento direto](direct-routing-plan.md) para obter detalhes.

Para atribuir um número de serviço, você precisará obter ou transferir os números de serviço de chamada tarifada ou gratuita existentes. Depois que você receber os números de telefone de serviço de chamada tarifada ou gratuita, eles serão exibidos no <!-- validate nav path --> **** > Número de**telefone**de**voz** > do centro de administração do Skype for Business, e o **tipo de número** listado será listado como **serviço de chamada**gratuita. Para obter seus números de serviço, consulte [obtendo números de telefone de serviço para o Skype for Business e o Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) ou, se você quiser transferir e número de serviço existente, consulte [transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, não poderá usar o centro de administração do Microsoft Teams para obter números de serviço. Em seguida, [gerencie os números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para ver como fazê-lo.
  
## <a name="related-topics"></a>Tópicos relacionados

[Veja aqui o que você obtém com o Sistema de Telefonia no Office 365](here-s-what-you-get-with-phone-system.md)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Exemplo de pequenas empresas - Configurar um atendedor automático](/microsoftteams/tutorial-org-aa)
