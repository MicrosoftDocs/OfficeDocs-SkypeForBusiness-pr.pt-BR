---
title: "Quais são os atendedores automáticos do sistema telefônico?"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
description: "Learn what Phone System (Cloud PBX) auto attendents are and how to use them. "
---

# Quais são os atendedores automáticos do sistema telefônico?

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](ab9f05a2-22cb-4692-a585-27f82d1b37c7.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/ab9f05a2-22cb-4692-a585-27f82d1b37c7). 
  
Sistema telefônico no Office 365 atendedores automáticos podem ser usados para criar um sistema de menu para sua organização que permite que os chamadores externos e internos mover através de um sistema de menu para localizar e coloque ou transferir chamadas para usuários de empresa ou departamentos na sua organização.
  
Quando as pessoas chamam, eles são apresentados com uma série de prompts de voz que ajudá-lo a fazer uma chamada para um usuário ou localizar alguém em sua organização e, em seguida, fazer uma chamada para esse usuário. Um atendedor automático é uma série de prompts de voz ou um arquivo de áudio que os chamadores ouvem em vez de um operador humano quando eles ligam para uma organização. Um atendedor automático permite que os chamadores mover por meio do sistema de menu, fazer chamadas, ou localize usuários usando um teclado do telefone (DTMF) ou usando o reconhecimento de fala de entradas de voz.
  
Para configurar um atendedor automático para o sistema telefônico no Office 365, [Configurar um atendedor automático de sistema telefônico](set-up-a-phone-system-auto-attendant.md).
  
Um atendedor automático de sistema telefônico tem os seguintes recursos:
  
- Ele oferece saudações corporativas ou informativas.
    
- Ele oferece menus corporativos personalizados. Você pode personalizar esses menus para ter mais do que um nível.
    
- Ele oferece pesquisa de diretório que permite que as pessoas que ligarem para pesquisar o diretório da organização para um nome.
    
- Ele permite que alguém chama alcançar ou deixar uma mensagem para uma pessoa em sua organização.
    
## Introdução

Para começar a usar os atendedores automáticos, é importante lembrar-se de que:
  
- Sua organização deve ter (no mínimo) uma licença Enterprise E3 plus **Sistema telefônico** ou uma licença Enterprise E5. O número de licenças de usuário do **Sistema telefônico** atribuídos impactos o número de serviço números que está disponível para ser usado para os atendedores automáticos. O número de atendedores automáticos que depende as números **Sistema telefônico** e **Conferência de áudio** licenças atribuídas em sua organização. Para saber mais sobre licenciamento,[Skype para Business e Teams Microsoft complemento licenciamento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Para redirecionar chamadas para um operador ou uma opção de menu que é um usuário com uma licença de **Sistema telefônico** Online, você precisará habilitá-las para o Enterprise Voice ou atribua chamando planos a eles. Consulte[Atribuir Skype para Business e Teams Microsoft licenças](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Você também pode usar o Windows PowerShell. Executar por exemplo:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obter e usar números de chamada gratuita serviço atendedores automáticos, você precisa configurar comunicações créditos. Para fazer isso, consulte [O que são créditos de comunicações?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) e[Configurar comunicações créditos para sua organização](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
    > [!IMPORTANT]
    > Os números de telefone (assinante) não podem ser atribuídos aos atendedores automáticos  somente números de telefone de serviço chamadas gratuitas ou tarifadas podem ser usados. 
  
## Visão geral do recurso

### Discar por Nome

Discagem por nome é um recurso de um atendedor automático que é conhecido como pesquisa no diretório. Ele permite que as pessoas que ligam para o atendedor automático para usar voz (reconhecimento de fala) ou o teclado do telefone (DTMF) para digitar um nome completo ou parcial para pesquisar diretório da empresa, localize a pessoa e depois que a chamada seja transferida para eles. Se você tiver o Skype for Business Online usuários, **elas não são necessárias para ter um número de telefone ou chamada planos atribuiu a eles, mas eles devem ter uma licença de **Sistema telefônico**** para que eles possam ser acessado ao pesquisarem usando discagem por nome. Discagem por nome ainda poderão localizar e transferir chamadas para Skype for Business Online usuários hospedados em diferentes países ou regiões para organizações multinacionais.
  
> [!CAUTION]
> Implantações locais de usuários do Lync Server 2010 não serão listadas no diretório quando alguém procura-los. 
  
### Tamanho máximo do diretório

Não há nenhum limite no tamanho do Active Directory para o qual discagem por nome é suportada quando usando o teclado do telefone para pesquisar para digitar nomes parciais ou total (nome sobrenome e também LastName + nome). No entanto, o tamanho máximo do nome da lista que um atendedor automático único pode oferecer suporte usando o reconhecimento de nome com a fala é 80.000 usuários.
  
||||
|:-----|:-----|:-----|
|**Tipo de entrada** <br/> |**Formato de pesquisa** <br/> |**Número máximo de usuários em uma organização** <br/> |
|DTMF (entrada de teclado)  <br/> |Parcial  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome  <br/> |Não há limite de hardware  <br/> |
|Fala (entrada de voz)  <br/> |Nome  <br/> Sobrenome  <br/> Nome + Sobrenome  <br/> Sobrenome + Nome  <br/> |80.000 usuários  <br/> |
   
> [!NOTE]
> Se você estiver usando discagem por nome com fala reconhecimento, mas o Active Directory da sua organização for maior do que 80.000 usuários e você ainda não limitado o escopo de discagem por nome usando o recurso de escopo de discagem, discagem por nome ainda funcionarão para os chamadores usando um teclado do telefone , e entradas de voz estará disponíveis para todos os outros cenários. Você pode usar o recurso de escopo de discagem para restringir os nomes que são acessíveis, alterando o escopo de discagem por nome para um atendedor automático particular. 
  
### Discar por Nome - entrada de teclado (DTMF)

Pessoas que estiver ligando podem usar discagem por nome alcançar usuários especificando tanto o nome completo ou parcial da pessoa que estão tentando alcançar. O bom, há vários formatos que podem ser usados quando o nome foi digitado.
  
Ao pesquisar o diretório de sua organização, as pessoas podem usar a tecla '0' (zero) para indicar um espaço entre o nome e o sobrenome ou sobrenome e nome. Quando eles estão inserindo o nome, serão solicitado a concluir a entrada do teclado com a tecla # (tecla jogo da velha). Por exemplo, "Depois que você inserir o nome da pessoa que está tentando contatar, pressione #". Se vários nomes forem localizados, a pessoa que liga receberá uma lista de nomes para escolher.
  
As pessoas podem pesquisar os nomes em sua organização usando os seguintes formatos de pesquisa em seu teclado de telefone:
  
|||||
|:-----|:-----|:-----|:-----|
|**Formato de nome** <br/> |**Tipo de pesquisa** <br/> |**Exemplo** <br/> |**Resultado de pesquisa** <br/> |
|Nome + Sobrenome  <br/> |Completo  <br/> |Amos0Marble#  <br/> |Amos Marble  <br/> |
|Sobrenome + Nome  <br/> |Completo  <br/> |Marble0Amos#  <br/> |Amos Marble  <br/> |
|Nome  <br/> |Completo  <br/> |Amos#  <br/> |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus  <br/> |
|Sobrenome  <br/> |Completo  <br/> |Marble#  <br/> |Pressione 1 para Amos Marble  <br/> Pressione 2 para Mary Marble  <br/> |
|Nome ou Sobrenome  <br/> |Parcial  <br/> |Mar#  <br/> |Pressione 1 para Mary Marble  <br/> Pressione 2 para Mary Jones  <br/> Pressione 3 para Amos Marcus  <br/> |
|Nome + Sobrenome  <br/> |Parcial  <br/> |Mar0Amos#  <br/> |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus  <br/> |
|Sobrenome + Nome  <br/> |Parcial  <br/> |Mar0Am#  <br/> |Pressione 1 para Amos Marble  <br/> Pressione 2 para Amos Marcus  <br/> |
   
Há vários caracteres especiais que são usadas quando pesquisando pessoas usando um teclado do telefone. Por exemplo, a pessoa será solicitada a usar a tecla de cerquilha (#), enquanto a tecla zero (0) é usada para um espaço entre nomes. Pressionar a tecla estrela (*) na lista de nomes para a pessoa correspondentes vai se repetir.
  
|||
|:-----|:-----|
|**Caractere de teclado de telefone especial** <br/> |**O que significa** <br/> |
|# (tecla jogo da velha)  <br/> |Caractere final ao inserir um nome.  <br/> |
|0 (zero)  <br/> |Espaço entre nomes.  <br/> |
|* (tecla asterisco)  <br/> |Repetir a lista de nomes correspondentes.  <br/> |
   
### Discar por Nome - Reconhecimento de nome pela fala

As pessoas podem pesquisar para que outras pessoas em sua organização usando voz dele (reconhecimento de fala). Eles também podem acessar qualquer pessoa no Active Directory da empresa dizendo o nome da pessoa que estão tentando localizar. Usar entradas de voz pode reconhecer nomes em vários formatos, incluindo o nome, sobrenome, nome sobrenome ou sobrenome + nome.
  
Quando você habilita o reconhecimento de fala para um atendedor automático, entrada de teclado do telefone (DTMF) não desabilitada, portanto, os dois tipos de entrada podem ser usados. Entrada de teclado do telefone não pode ser desabilitada e pode ser usada a qualquer momento, mesmo se o reconhecimento de fala é habilitado no atendedor automático.
  
Como com a entrada de teclado de telefone, se vários nomes forem localizados, a pessoa que liga receberá uma lista de nomes para escolher.
  
As pessoas que ligarem poderão falar os nomes nos seguintes formatos:
  
|||||
|:-----|:-----|:-----|:-----|
|**Nome com fala** <br/> |**Tipo de pesquisa** <br/> |**Exemplo** <br/> |**Resultado de pesquisa** <br/> |
|Nome + Sobrenome  <br/> |Completo  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|Sobrenome + Nome  <br/> |Completo  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|Nome  <br/> |Completo  <br/> |Amos  <br/> |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Amos Jones  <br/> |
|Sobrenome  <br/> |Completo  <br/> |Marble  <br/> |Pressione ou fale 1 para Amos Marble  <br/> Pressione ou fale 2 para Ben Marble  <br/> |
   
> [!NOTE]
> Poderá demorar até 36 horas para um novo usuário ter seu nome listado no diretório de discagem por nome com o reconhecimento de fala. 
  
### Idioma de suporte

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
   
Os seguintes comandos de voz estão disponíveis nos quatorze (14﻿) idiomas aceitos para reconhecimento e fala:
  
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
   
### Usando a opção do operador

Usar o operador para um atendedor automático é uma configuração opcional que fornece ao chamador a opção de falar com uma pessoa.
  
A tecla 0 e o comando de voz "Operador" (em todos os idiomas aceitos para reconhecimento de voz) são atribuídos ao operador por padrão.
  
> [!NOTE]
> Você pode definir o botão que é enviado para o **operador** para uma chave diferente usando as **Opções de Menu**. 
  
Você pode definir o seguinte como o operador:
  
- Um Skype para Business Online usuário que tem um **Sistema telefônico** licença que está habilitada para Enterprise Voice ou tem planos de chamada atribuídos a eles. Você pode configurá-lo para a pessoa que estiver ligando possa ser enviada para a caixa postal. Para fazer isso, selecione uma **pessoa na sua empresa** e defina chamadas desta pessoa automaticamente sejam encaminhadas diretamente para a caixa postal.
    
    > [!NOTE]
    > Os usuários hospedados no local usando o Lync Server 2010 não pode ser usado como um operador. 
  
- Outro atendedor automático que é configurado para sua organização.
    
- Qualquer fila de chamada existente configurada em sua organização. Para ver mais informações sobre filas de chamada, consulte [Criar uma fila de chamada do sistema telefônico](create-a-phone-system-call-queue.md).
    
### Horários comerciais e administração de chamada

Horário comercial é definido em cada atendedor automático. Se não estiverem horário comercial, todos os dias e todas as horas do dia são consideradas horário comercial porque um cronograma de 24/7 é definido por padrão. Horário comercial pode ser definido com quebras no tempo durante o dia e todas as horas que não estão definidas como horário comercial é considerado fora do horário comercial. Você pode definir opções de tratamento de chamada de entrada diferentes e saudações diferentes (que são opcionais) e ambos podem ser definidos para horário comercial e fora do horário comercial.
  
Cada atendedor automático tem opções de tratamento de chamada que podem ser definidas:
  
- Você pode ter a chamada desconectada logo após a saudação.
    
- Também é possível:
    
  - Redirecionar a chamada para um Skype for Business Online usuário que tenha uma licença de **Sistema telefônico** que está habilitada para Enterprise Voice ou planos de chamar atribuiu a elas. Você pode configurá-lo para a pessoa que estiver ligando possa ser enviada para a caixa postal. Para fazer isso, selecione uma **pessoa na sua empresa** e defina chamadas desta pessoa automaticamente sejam encaminhadas diretamente para a caixa postal.
    
    > [!NOTE]
    > Os usuários hospedados no local usando o Lync Server 2010 não são suportados. 
  
  - Redirecione a chamada para uma fila de chamada. Para ver mais informações sobre filas de chamada, consulte [Criar uma fila de chamada do sistema telefônico](create-a-phone-system-call-queue.md).
    
  - Redirecionar a chamada para outro atendedor automático que você tenha configurado.
    
- Criar opções de menu e reproduzir o prompt do menu para o chamador. Por exemplo: "Pressione 1 para Vendas, Pressione 2 para Serviços. Para falar com o operador, pressione 0 a qualquer momento."
    
### Opções do menu

Os atendedores de automáticos de sistema telefônico permitem que você criar prompts de menu ("Pressione 1 para vendas, pressione 2 para serviços") e definir as opções de menu para rotear chamadas com base no que o usuário seleciona. Configurar opções de menu para um atendedor automático permite que uma organização fornecer um guia interativo para acessar a pessoa seu destino mais rápido, sem depender de um operador para lidar com as chamadas de entrada. Avisos de menu podem ser criados usando o texto em fala (avisos gerados pelo sistema) ou carregar um arquivo de áudio que tenha sido registrado. Reconhecimento de fala usa comandos de voz para navegação viva-voz, mas pessoas chamando também podem usar o teclado do telefone para navegar em menus.
  
Teclas 0 a 9 podem ser atribuídas para **Opções de Menu** em um atendedor automático usando o Skype para o Centro de administração de negócios. Diferentes conjuntos de opções do menu podem ser criados para horário comercial e depois de horas e você pode habilitar ou desabilitar a discagem por nome nas **Opções de Menu**. Chaves podem ser mapeadas para transferir as chamadas para:
  
- Um operador, que é mapeado para chave 0 por padrão. No entanto, pode ser atribuído novamente a qualquer outra chave, ou removido do menu.
    
- Uma fila de chamada.
    
- Outro atendedor automático. Menus de vários níveis podem ser configurados apontando uma **Opção de Menu** no atendedor automático de um para outro atendedor automático com seu próprio conjunto de opções de Menu, que é chamado de um atendedor automático "aninhadas".
    
- Um Skype para Business Online usuário que tem um **Sistema telefônico** licença que está habilitada para Enterprise Voice ou tem planos de chamada atribuídos a eles. Você pode configurá-lo para a pessoa que estiver ligando possa ser enviada para a caixa postal. Para fazer isso, selecione uma **pessoa na sua empresa** e defina chamadas desta pessoa automaticamente sejam encaminhadas diretamente para a caixa postal.
    
    > [!NOTE]
    > Os usuários hospedados no local usando o Lync Server 2010 não pode ser usado nas **Opções de Menu**. 
  
O nome de cada opção de menu torna-se uma palavra-chave de reconhecimento de fala se tiver sido habilitado o reconhecimento de fala. Por exemplo, os chamadores podem dizer "Um" para selecionar a opção de menu mapeada para chave 1 ou simplesmente dizem "Vendas" para selecionar a opção de menu mesmo denominada "Vendas".
  
Para configurar um atendedor automático e as opções de menu, vá [Configurar um atendedor automático de sistema telefônico](set-up-a-phone-system-auto-attendant.md).
  
### Como obter números de serviço para um atendedor automático

Antes de poder criar e configurar atendedores automáticos, você precisará obter ou transferir sua chamada Tarifada existente ou serviço de chamada gratuito números. Quando você receber a chamada Tarifada ou números de telefone de chamada gratuita do serviço, eles aparecerão no **Skype para o Centro de administração de negócios** > **voz** > **números de telefone** e o será do **tipo de número** listado será listado como **serviço - chamada gratuito**. Para obter seus números de serviço, consulte [Obtendo números telefônicos de serviço do Skype for Business](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) ou, se desejar transferir e número de serviço existente, consulte[Transferir números de telefone para o Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, você não pode usar o Skype para o Centro de administração de negócios para obter números de serviço. [Gerenciar números de telefone para sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , em vez para ver como fazer isso.
  
## Alterando a ID de chamador do usuário para ser o número de telefone de uma chamada de fila

Você pode proteger a identidade do usuário, alterando sua ID de chamador para as chamadas de saída para uma fila de chamada em vez disso, criando uma política usando o cmdlet **New-CallingLineIdentity**.
  
Para fazer isso, execute:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Aplique a política ao usuário usando o cmdlet **Grant-CallingLineIdentity**. Para fazer isso, execute:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Você pode obter mais informações sobre como fazer alterações nas configurações de ID do chamador na sua organização [Como a identificação de chamadas pode ser usada em sua organização](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## Tópicos Relacionados

[Veja aqui o que você obtém com sistema telefônico no Office 365](here-s-what-you-get-with-phone-system-in-office-365.md)
  
[Configurar planos de chamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

