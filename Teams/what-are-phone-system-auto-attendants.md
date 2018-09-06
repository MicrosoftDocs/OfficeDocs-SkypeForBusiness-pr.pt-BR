---
title: O que são atendedores automáticos do Sistema de Telefonia?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba quais são os atendedores automáticos de sistema telefônico (nuvem PBX) e como usá-los. '
ms.openlocfilehash: 31a9a9c7a292014cac01909274b7d5de1b640655
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23784778"
---
# <a name="what-are-phone-system-auto-attendants"></a>O que são atendedores automáticos do Sistema de Telefonia?

O sistema telefônico no Office 365 atendedores automáticos podem ser usados para criar um sistema de menu para a sua organização que permite que os chamadores externos e internos mover através de um sistema de menu localizar e colocar ou transferir chamadas para usuários da empresa ou departamentos na organização.
  
Quando as pessoas ligam, elas ouvem uma série de mensagens de voz que as ajudam a fazer uma chamada para um usuário ou localizar alguém em sua organização e depois fazer uma chamada para aquele usuário. Um atendedor automático é uma série de prompts de voz ou um arquivo de áudio que os chamadores ouvem, em vez de um operador humano quando ele liga para uma organização. Um atendedor automático permite que os chamadores se movam pelo sistema de menus, façam chamadas ou localizem usuários usando um teclado de telefone (DTMF) ou entradas de voz usando reconhecimento de voz. 
  
Para configurar um atendedor automático para o sistema telefônico no Office 365, vá [Configurar um atendedor automático de sistema telefônico](/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).
  
Um atendedor automático de sistema telefônico tem os seguintes recursos:
  
- Ele oferece saudações corporativas ou informativas.
    
- Ele oferece menus corporativos personalizados. Você pode personalizar esses menus para ter mais do que um nível.
    
- Ele fornece pesquisa de diretório que permite que as pessoas que ligam para pesquisar o diretório da organização para um nome.
    
- Ele permite que uma pessoa que chama para alcançar ou deixar uma mensagem para uma pessoa em sua organização.
    
## <a name="getting-started"></a>Introdução

Para começar a usar os atendedores automáticos, é importante lembrar-se de que:
  
- Sua organização deve ter (no mínimo), uma licença Enterprise E3 plus **Sistema telefônico** ou uma licença Enterprise E5. O número de licenças de usuário do **Sistema telefônico** que receberem o impacto sobre o número de serviço números que está disponível a serem usados para atendedores automáticos. O número de atendedores automáticos que depende das licenças de **Sistema telefônico** e **Audioconferência** números que são atribuídas em sua organização. Para saber mais sobre o licenciamento, vá [Skype para licenciamento de complemento de negócios e equipes da Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
    > [!TIP]
    > Para redirecionar chamadas para um operador ou uma opção de menu que é um usuário Online com uma licença de **Sistema telefônico** , você precisará habilitá-los para o Enterprise Voice ou atribuir chamar planos para acessá-los. Consulte[Atribuir Skype para licenças de negócios e equipes da Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). Você também pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obter e usar números gratuitos de serviço para seus atendedores automáticos, você precisará configurar créditos de comunicações. Para fazer isso, consulte [Cite Communications créditos?](what-are-communications-credits.md) e [Configurar créditos de comunicações para sua organização](set-up-communications-credits-for-your-organization.md).
    
    > [!IMPORTANT]
    > [!IMPORTANTE] Os números de telefone (assinante) não podem ser atribuídos aos atendedores automáticos  somente números de telefone de serviço chamadas gratuitas ou tarifadas podem ser usados. 
  
## <a name="feature-overview"></a>Visão geral do recurso

### <a name="dial-by-name"></a>Discar por Nome

O Discar por Nome é um recurso do atendedor automático conhecido como pesquisa de diretório. Ele permite que as pessoas que ligam para o atendedor automático para usar voz (reconhecimento de fala) ou do teclado do telefone (DTMF) para inserir um nome completo ou parcial para pesquisar o diretório da empresa, localizar a pessoa e, em seguida, tem transferir a chamada para eles. Se você tiver Skype para usuários corporativos Online, **eles não são necessários para ter um número de telefone ou chamar planos atribuiu a eles, mas devem ter uma licença de sistema telefônico** para que eles possam ser alcançados quando eles pesquisam usando discagem por nome. Discagem por nome ainda poderão localizar e transferir chamadas para Skype para usuários corporativos Online que são hospedados em diferentes países ou regiões para organizações multinacionais.
  
> [!CAUTION]
> Implantações em instalações de usuários do Lync Server 2010 não serão listadas no diretório, quando alguém procura-los. 
  
### <a name="maximum-directory-size"></a>Tamanho máximo do diretório

Não há nenhum limite do tamanho do Active Directory para o qual a discagem por nome é suportada ao usar o teclado do telefone a ser pesquisado para digitar nomes parciais ou completos (FirstName + LastName e também LastName + FirstName). No entanto, o tamanho máximo do nome da lista que um atendedor automático único pode dar suporte usando o reconhecimento de nome com fala é 80.000 usuários.
  
||||
|:-----|:-----|:-----|
|**Tipo de entrada** <br/> |**Formato de pesquisa** <br/> |**Número máximo de usuários em uma organização** <br/> |
|DTMF (entrada de teclado)  <br/> |Parcial  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome  <br/> |Não há limite de hardware  <br/> |
|Fala (entrada de voz)  <br/> |FirstName  <br/> LastName  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome  <br/> |80.000 usuários  <br/> |
   
> [!NOTE]
> Se você estiver usando a discagem pelo nome, com a fala reconhecimento, mas o Active Directory da sua organização for maior que 80.000 usuários e você ainda não limitados o escopo da discagem por nome usando o recurso de escopo de discagem, a discagem por nome funcionará para os chamadores usando um teclado do telefone , e entradas de voz estarão disponíveis para todos os outros cenários. Você pode usar o recurso Escopo de Discagem para restringir os nomes que são acessíveis mudando o escopo da Discagem por Nome para um atendedor automático específico. 
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Discar por Nome - entrada de teclado (DTMF)

Pessoas chamando em podem usar discagem pelo nome, para atingir usuários especificando-se tanto o nome completo ou parcial da pessoa que estão tentando fazer contato. O BOM é que não há vários formatos que podem ser usados quando o nome é inserido.
  
Ao pesquisar o diretório de sua organização, as pessoas podem usar a tecla '0' (zero) para indicar um espaço entre o nome e o sobrenome ou sobrenome e nome. Quando eles estão inserindo o nome, serão solicitado a concluir a entrada do teclado com a tecla # (tecla jogo da velha). Por exemplo, "Depois que você inserir o nome da pessoa que está tentando contatar, pressione #". Se vários nomes forem localizados, a pessoa que liga receberá uma lista de nomes para escolher.
  
As pessoas podem pesquisar os nomes em sua organização usando os seguintes formatos de pesquisa em seu teclado de telefone:
  
|||||
|:-----|:-----|:-----|:-----|
|**Formato de nome** <br/> |**Tipo de pesquisa** <br/> |**Exemplo** <br/> |**Resultado de pesquisa** <br/> |
|Nome + Sobrenome  <br/> |Completo  <br/> |Amos0Marble#  <br/> |Amos Marble  <br/> |
|Sobrenome + Nome  <br/> |Completo  <br/> |Marble0Amos#  <br/> |Amos Marble  <br/> |
|FirstName  <br/> |Completo  <br/> |Amos#  <br/> |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus  <br/> |
|LastName  <br/> |Completo  <br/> |Marble#  <br/> |Pressione 1 para Amos Marble  <br/> Pressione 2 para Mary Marble  <br/> |
|Nome ou Sobrenome  <br/> |Parcial  <br/> |Mar#  <br/> |Pressione 1 para Mary Marble  <br/> Pressione 2 para Mary Jones  <br/> Pressione 3 para Amos Marcus  <br/> |
|Nome + Sobrenome  <br/> |Parcial  <br/> |Mar0Amos#  <br/> |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus  <br/> |
|Sobrenome + Nome  <br/> |Parcial  <br/> |Mar0Am#  <br/> |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus  <br/> |
   
Há vários caracteres especiais que são usados durante a pesquisa de pessoas por meio de um teclado de telefone. Por exemplo, a pessoa será solicitada a usar a tecla de cerquilha (#), enquanto a tecla zero (0) é usada para um espaço entre os nomes. Pressionar a tecla asterisco (*) repetirá a lista de nomes correspondentes para a pessoa.
  
|||
|:-----|:-----|
|**Caractere de teclado de telefone especial** <br/> |**O que significa** <br/> |
|# (tecla jogo da velha)  <br/> |Caractere final ao inserir um nome.  <br/> |
|0 (zero)  <br/> |Espaço entre nomes.  <br/> |
|* (tecla asterisco)  <br/> |Repetir a lista de nomes correspondentes.  <br/> |
   
### <a name="dial-by-name---name-recognition-with-speech"></a>Discar por Nome - Reconhecimento de nome pela fala

Pessoas podem pesquisar para outras pessoas em sua organização usando sua voz (reconhecimento de fala). Eles também podem alcançar qualquer pessoa Active Directory da empresa dizendo o nome da pessoa que estão tentando localizar. Usar as entradas de voz pode reconhecer nomes em vários formatos, incluindo FirstName, LastName, FirstName + LastName, ou LastName + FirstName.
  
Quando você habilita o reconhecimento de fala para um atendedor automático, entrada de teclado do telefone (DTMF) não será desabilitada para que ambos os tipos de entrada que possam ser usados. Entrada de teclado do telefone não pode ser desabilitada e pode ser usada a qualquer momento, mesmo se o reconhecimento de fala estiver habilitado no atendedor automático.
  
Como com a entrada de teclado de telefone, se vários nomes forem localizados, a pessoa que liga receberá uma lista de nomes para escolher.
  
As pessoas que ligarem poderão falar os nomes nos seguintes formatos:
  
|||||
|:-----|:-----|:-----|:-----|
|**Nomeie com a fala** <br/> |**Tipo de pesquisa** <br/> |**Exemplo** <br/> |**Resultado de pesquisa** <br/> |
|Nome + Sobrenome  <br/> |Completo  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|Sobrenome + Nome  <br/> |Completo  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|FirstName  <br/> |Completo  <br/> |Amos  <br/> |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Amos Jones  <br/> |
|LastName  <br/> |Completo  <br/> |Marble  <br/> |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Ben Marble  <br/> |
   
> [!NOTE]
> Poderá demorar até 36 horas para um novo usuário ter seu nome listado no diretório para discagem por nome com reconhecimento de fala. 
  
### <a name="language-support"></a>Idioma de suporte

Os seguintes idiomas estão disponíveis para conversão de texto em fala:
  
||||
|:-----|:-----|:-----|
|Árabe (EG)  <br/> |Inglês (NZ)  <br/> |Coreano (KO)  <br/> |
|Chinês (HK)  <br/> |Inglês (Reino Unido)  <br/> |Noruega (NO)  <br/> |
|Chinês (TW)  <br/> |Inglês (EUA)  <br/> |Polonês (PL)  <br/> |
|Chinês (ZH)  <br/> |Finlandês (FI)  <br/> |Português (BR)  <br/> |
|Dinamarquês (DA)  <br/> |Francês (CA)  <br/> |Português (PT)  <br/> |
|Holandês (NL)  <br/> |Francês (FR)  <br/> |Russo (RU)  <br/> |
|Inglês (AU)  <br/> |Alemão (DE)  <br/> |Espanhol (ES)  <br/> |
|Inglês (CA)  <br/> |Italiano (IT)  <br/> |Espanhol (MX)  <br/> |
|Inglês (IN)  <br/> |Japonês (JP)  <br/> |Sueco (SV)  <br/> |
   
O reconhecimento de fala para atendedores automáticos está disponível nos seguintes idiomas:
  
|||
|:-----|:-----|
|Chinês (ZH)  <br/> |Francês (FR)  <br/> |
|Inglês (AU)  <br/> |Alemão (DE)  <br/> |
|Inglês (CA)  <br/> |Italiano (IT)  <br/> |
|Inglês (IN)  <br/> |Japonês (JP)  <br/> |
|Inglês (Reino Unido)  <br/> |Português (BR)  <br/> |
|Inglês (EUA)  <br/> |Espanhol (ES)  <br/> |
|Francês (CA)  <br/> |Espanhol (MX)  <br/> |
   
Os seguintes comandos de voz estão disponíveis nos quatorze (14) idiomas aceitos para reconhecimento e fala:
  
|||
|:-----|:-----|
|**Comando de voz** <br/> |**Significado** <br/> |
|Sim  <br/> |Sim - corresponde ao pressionamento 1 para Sim.  <br/> |
|Não  <br/> |Não corresponde ao pressionamento 2 para Não  <br/> |
|Repetir  <br/> |Repete a lista de opções - corresponde a pressionar * repetir a lista de opções.  <br/> |
|Operador  <br/> |Sessão de grupo para operador - corresponde a pressionar 0 para "Operador".  <br/> |
|Menu Principal  <br/> |Leva o chamador para o menu principal do atendedor automático.  <br/> |
|Zero  <br/> |Corresponde a pressionar 0 (por padrão, o mesmo que "Operador").  <br/> |
|Um  <br/> |Corresponde a pressionar 1.  <br/> |
|Dois  <br/> |Corresponde a pressionar 2.  <br/> |
|Três  <br/> |Corresponde a pressionar 3.  <br/> |
|Quatro  <br/> |Corresponde a pressionar 4.  <br/> |
|Cinco  <br/> |Corresponde a pressionar 5.  <br/> |
|Seis  <br/> |Corresponde a pressionar 6.  <br/> |
|Sete  <br/> |Corresponde a pressionar 7.  <br/> |
|Oito  <br/> |Corresponde a pressionar 8.  <br/> |
|Nove  <br/> |Corresponde a pressionar 9.  <br/> |
   
### <a name="using-the-operator-option"></a>Usando a opção do operador

Usar o operador para um atendedor automático é uma configuração opcional que fornece ao chamador a opção de falar com uma pessoa.
  
A tecla 0 e o comando de voz "Operador" (em todos os idiomas aceitos para reconhecimento de voz) são atribuídos ao operador por padrão.
  
> [!NOTE]
> Você pode definir o botão que é enviado para o **operador** a uma chave diferente usando as **Opções de Menu**. 
  
Você pode definir o seguinte como o operador:
  
- Um Skype para usuário Business Online que tem um **Sistema telefônico** licenciar que esteja habilitado para Enterprise Voice ou chamar planos atribuiu a eles. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para isso, selecione uma **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal.
    
    > [!NOTE]
    > Usuários hospedados no local usando o Lync Server 2010 não pode ser usado como um operador. 
  
- Outro atendedor automático que é configurado para sua organização.
    
- Qualquer fila de chamada existente que é configurada em sua organização. Para obter mais informações sobre filas de espera de chamada, consulte [criar uma fila de chamada do sistema telefônico](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).
    
### <a name="business-hours-and-call-handling"></a>Horários comerciais e administração de chamada

Os horários comerciais são definidos em cada atendedor automático. Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão. Horário comercial podem ser definido com quebras em tempo durante o dia e todos os horários que não são definidos como horários comerciais são considerados fora do horário comercial. Você pode definir diferentes opções de atendimento de chamadas recebidas e saudações diferentes (que são opcionais), e ambas podem ser definidas para horário comercial e fora do horário comercial.
  
Cada atendedor automático tem opções de atendimento de chamadas que podem ser definidas:
  
- Você pode ter a chamada desconectada logo após a saudação.
    
- Também é possível:
    
  - Redirecionar a chamada para um Skype para usuário Business Online que tem uma licença de **Sistema telefônico** que esteja habilitado para Enterprise Voice ou chamar planos atribuiu a eles. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para isso, selecione uma **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal.
    
    > [!NOTE]
    > Usuários hospedados no local usando o Lync Server 2010 não são suportados. 
  
  - Redirecione a chamada para uma fila de espera de chamada. Para obter mais informações sobre filas de espera de chamada, consulte [criar uma fila de chamada do sistema telefônico](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).
    
  - Redirecione a chamada para outro atendedor automático que você definiu.
    
- Criar opções de menu e reproduzir o prompt do menu para o chamador. Por exemplo: "Pressione 1 para Vendas, Pressione 2 para Serviços. Para falar com o operador, pressione 0 a qualquer momento."
    
### <a name="menu-options"></a>Opções do menu

Atendedores automáticos da telefone sistema permitem que você crie os prompts de menu ("Pressione 1 para vendas, pressione 2 para serviços") e defina as opções de menu para rotear chamadas com base em que o usuário seleciona. A configuração das opções de menu de um atendedor automático permite que uma organização forneça orientação interativa para levar a pessoa a seu destino mais rápido, sem contar com um operador humano para administrar as chamadas de entrada. Os prompts de menu podem ser criados usando texto em fala (gerada pelo sistema prompts) ou carregando um arquivo de áudio que foi registrado. O reconhecimento de fala usa comandos de voz para navegação sem usar as mãos, mas os chamadores também podem usar o teclado do telefone para navegar pelos menus.
  
Teclas 0 a 9 podem ser atribuídas às **Opções de Menu** em um atendedor automático usando o Skype para o Centro de administração de negócios. Diferentes conjuntos de opções de menu podem ser criadas para os horários comerciais e horários fora do expediente, e você pode habilitar ou desabilitar o Discar por Nome nas **Opções de Menu**. As teclas podem ser mapeadas para transferir as chamadas para:
  
- Um operador, que é mapeado para a tecla 0 por padrão. No entanto, ele pode ser novamente atribuído a qualquer outra tecla, ou removido do menu.
    
- Uma fila de espera de chamada.
    
- Outro atendedor automático. Menus de vários níveis podem ser configuradas pelo apontando uma **Opção de Menu** no atendedor automático de um para o outro atendedor com seu próprio conjunto de opções de Menu, que é chamado um atendedor automático "aninhados".
    
- Um Skype para usuário Business Online que tem um **Sistema telefônico** licenciar que esteja habilitado para Enterprise Voice ou chamar planos atribuiu a eles. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para isso, selecione uma **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal.
    
    > [!NOTE]
    > Usuários hospedados no local usando o Lync Server 2010 não pode ser usado no **Menu Opções**. 
  
O nome de cada opção de menu torna-se uma palavra-chave de reconhecimento de fala, se tiver sido habilitado o reconhecimento de fala. Por exemplo, os chamadores podem dizer "One" para selecionar a opção de menu mapeada para a tecla 1 ou simplesmente dizem "Sales" para selecionar a opção de menu mesmo chamada "Sales".
  
Para configurar um atendedor automático e as opções de menu, vá [Configurar um atendedor automático de sistema telefônico](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).
  
### <a name="getting-service-numbers-for-an-auto-attendant"></a>Como obter números de serviço para um atendedor automático

Antes de você poder criar e configurar os atendedores automáticos, será necessário receber ou transferir os números de serviço de chamada gratuita ou tarifada. Depois que você fazer a chamada Tarifada ou números de telefone gratuitos de serviço, eles serão exibidos no **Skype para centro de administração de negócios** > **voz** > **números de telefone**e a disposição de **tipo de número** listado listada como **serviço - chamada gratuita **. Para obter seus números de serviço, consulte [Getting números de telefone de serviço para Skype para equipes da Microsoft e de negócios](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) ou se você deseja transferir e o número de serviço existente, consulte [transferir os números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, você não pode usar o Skype para centro de administração de negócios para obter os números de serviço. Vá [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez disso, para ver como fazê-lo.
  
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Alterar a identificação de chamadas do usuário para um número de telefone de fila de chamadas

Você pode proteger a identidade de um usuário alterando a identificação de chamadas dele para chamadas de saída para uma fila de chamadas criando uma política com o cmdlet **New-CallingLineIdentity**.
  
Para fazer isso, execute:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Então, aplique a política ao usuário usando o cmdlet **Grant-CallingLineIdentity**. Para fazer isso, execute:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Você pode obter mais informações sobre como fazer alterações nas configurações de ID de chamador em sua organização [como ID do chamador pode ser usado na sua organização](/SkypeForBusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).
  
## <a name="related-topics"></a>Tópicos relacionados
[Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365](here-s-what-you-get-with-phone-system.md)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 