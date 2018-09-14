---
title: Comparação de recursos do cliente móvel para Skype para negócios
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Resumo: Revise o suporte de recurso para o cliente móvel durante o planejamento de Skype para Business Server.'
ms.openlocfilehash: f04d0162113db68e2507930e827904110b69066f
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965745"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Comparação de recursos do cliente móvel para Skype para negócios
 
**Resumo:** Revise o suporte de recurso para o cliente móvel durante o planejamento de Skype para Business Server.
  
Este artigo compara os recursos e capacidades entre Skype para clientes móveis de negócios e do Skype para o cliente de desktop corporativos nas seguintes categorias:
  
- Conexão, notificações por push e recursos gerais
    
- Presença avançada
    
- Contatos e grupos de contato
    
- IM (sistema de mensagens instantâneas)
    
- Skype para a Skype para negócios de áudio e vídeo de negócios
    
- Conferência
    
- Telefonia
    
- Usuários externos
    
- Arquivamento e conformidade
    
-  Autenticação moderna
    
As tabelas a seguir listam os recursos que estão disponíveis para Skype para usuários comerciais em uma implantação local do Skype para Business Server. Os mesmos recursos também estão disponíveis para Skype para usuários corporativos Online e o Microsoft Office 365, a menos que indicado de outra forma nas notas de rodapé de tabela.
  
> [!NOTE]
> Para obter ajuda online e recursos para usuários finais, consulte [Skype descobrir para a empresa](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Para comparar os recursos disponíveis em outro Skype para clientes corporativos, consulte [comparação de recursos do cliente de Desktop do Skype para negócios](desktop-feature-comparison.md). 

> [!NOTE]
> Suporte MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype para Business Server 2019. Todos os Skype atual para clientes móveis do Business já use Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Usuários com clientes herdados usando MCX serão necessário atualizar para um cliente atual.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Conexão, notificações por push e recursos gerais

 
 | Recurso/capacidade  | Skype para o cliente de desktop de negócios  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype para sessão de negócios permanece conectada no  <br/> |& #x 2714;|& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |& #x 2714;|
|Suporte para notificações de push  <br/> |& #x 2714; & #x 2778; |& #x 2714;|& #x 2714;|& #x 2714;|
|As informações de conta de vários usuários podem ser armazenadas em cache no mesmo dispositivo  <br/> |& #x 2714;||||
|Leitor de tela/voice over  <br/> |& #x 2714;|& #x 2714; & #x 2777;           Apenas em inglês  <br/> |& #x 2714;|& #x 2714;|
|Use um teclado externo para acessibilidade  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|
|Apoio ao Programa de Aperfeiçoamento da Experiência do Usuário  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
   
 & #x 2776;  No Windows Phone, Skype para negócios desconecta-se automaticamente após um período de inatividade, da seguinte maneira:
  
- Se o usuário habilitou notificações de push, o Skype para negócios desconecta-se após 10 dias de inatividade.
    
- Se o usuário não habilitou notificações de push, Skype para negócios desconecta-se assim que o usuário deixa o aplicativo.
    
Em dispositivos iOS, Skype para negócios desconecta-se automaticamente depois que o cliente móvel não tem contatar o servidor para 10 dias devido à perda de conectividade de rede ou outros problemas.
  
 & #x 2777;  No aplicativo.
  
 & #x 2778;  As notificações estão disponíveis quando o aplicativo está sendo executado em segundo plano.
  
## <a name="enhanced-presence-support"></a>Suporte para presença avançada


 | Recurso/capacidade  | Skype para o cliente de desktop de negócios  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publicar e exibir status  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Exibir status com base nas informações de disponibilidade de calendário  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Exibir notas de status e mensagens de Ausência Temporária  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Adicionar um local personalizado  <br/> |& #x 2714;||||
|Adicionar uma nota personalizada  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Publicar status com base na informação de disponibilidade do calendário   <br/> |& #x 2714; & #x 2776; ||||
|Definir estado de presença manual (como Ocupado, Não Incomodar e assim por diante)  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
   
 & #x 2776;  Skype para clientes móveis de negócios não atualizar a presença de um usuário com base nas informações de disponibilidade de calendário do usuário. Se um usuário do cliente móvel também é conectado ao Skype para o cliente de desktop de negócios, o cliente de desktop atualiza a presença do usuário com base nas informações de disponibilidade de calendário do usuário. Se o usuário está conectado ao apenas um cliente móvel, a presença do usuário não é atualizada com base nas informações de disponibilidade informações de calendário.
  
## <a name="contacts-and-contact-groups-support"></a>Suporte para contatos e grupos de contatos


 | Recurso/capacidade  | Skype para o cliente de desktop de negócios  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Exibir lista de contatos  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Exibir grupos de contato  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Exibir grupos de contatos frequentes  <br/> |& #x 2714;||||
|Modificar lista de contatos  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Marcar contatos para alertas de alteração de status  <br/> |& #x 2714;||||
|Controlar relações de privacidade  <br/> |& #x 2714;||||
|Pesquisar o catálogo de endereços corporativo  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Pesquisar lista de contatos  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Gerenciar grupos de contatos  <br/> |& #x 2714;|||& #x 2714;|
|Expandir grupos de distribuição  <br/> |& #x 2714;|& #x 2714;||& #x 2714;|
|Pesquisar grupos de resposta  <br/> |& #x 2714; & #x 2776; |& #x 2714;||& #x 2714;|
|Exibir ou ocultar fotos do contato  <br/> |& #x 2714;|& #x 2714;|||
|Fixe um contato em sua tela inicial  <br/> ||& #x 2714;|||
   
 & #x 2776;  Não disponível para Skype para usuários corporativos Online e/ou Office 365.
  
## <a name="instant-messaging-support"></a>Suporte ao sistema de mensagens instantâneas


 | Recurso/capacidade  | Skype para o cliente de desktop de negócios  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar IM (sistema de mensagens instantâneas) com um contato  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Participar de IM com vários participantes  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Convidar outros por uma janela de conversa  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Exibir conversas atuais  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Navegar entre várias conversas de IM  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Fazer o login automaticamente de conversas de IM no Exchange  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Enviar uma conversa de IM como uma mensagem de email  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Iniciar um email para um contato  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Exibir convites de IM perdidos  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Vibrar com IM em entrada  <br/> ||& #x 2714; & #x 2776; |& #x 2714;|& #x 2714;|
   
 & #x 2776;  Este dispositivo vibra cada vez que uma IM é recebida, mesmo se a mensagem atual na conversa de IM é exibida
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype para a Skype para negócios de áudio e vídeo de negócios


 | Recurso/funcionalidade  | Skype para o cliente de desktop de negócios  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype para negócios para Skype para voice de negócios  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Skype para negócios para Skype para vídeo de negócios  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
   
> [!NOTE]
> Por padrão, o vídeo em um dispositivo móvel requer uma conexão Wi-Fi.  
  
## <a name="conferencing-support"></a>Suporte a conferências


 | Recurso/capacidade  | Skype para o cliente de desktop de negócios  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Clicar em um link no lembrete de reunião para participar de uma reunião com vídeo ou VoIP  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Participar de IM com vários participantes  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Usar a conferência discada (o servidor chama o dispositivo móvel)  <br/> |& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |
|Usar conferência de áudio discada  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Exibir vídeo da reunião  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Exibir vídeo com vários participantes (modo de exibição de galeria)  <br/> |& #x 2714;||||
|Aguardar no lobby da reunião  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Usar os controles do apresentador na reunião  <br/> |& #x 2714;||||
|Acessar lista de participação da reunião detalhada para conferências de áudio  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Acessar lista de participação da reunião detalhada para conferências de IM  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Compartilhar área de trabalho ou programa  <br/> |& #x 2714;||||
|Exibir a área de trabalho compartilhada ou programa (VbSS ou RDP)  <br/> |& #x 2714;|& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |
|Exibir arquivos compartilhados do PowerPoint  <br/> |& #x 2714;|& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |
|Carregar e apresentar arquivos do PowerPoint  <br/> |& #x 2714;||& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |
|Usar ferramentas de reunião (usar quadro de comunicações, conduzir votações, compartilhar arquivos)  <br/> |& #x 2714;||||
|Navegar por uma lista de suas reuniões  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Ingressar em uma reunião, mesmo se você não tiver um Skype para a conta de negócios  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Visualize mais informações sobre os participantes da reunião  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Inicie uma conversa de grupo não agendada com vários participantes diretamente de seu cliente ou dispositivo   <br/> |& #x 2714;|& #x 2714;|& #x 2714;||
   
 & #x 2776;  Para usuários do Office 365, esse recurso exige Enterprise Voice, o que faz parte da licença E5.
  
 & #x 2777;  Requer uma conexão WiFi por padrão.
  
## <a name="telephony-support"></a>Suporte a telefonia


 | Recurso/capacidade  | Skype para o cliente de desktop de negócios  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|No Skype para os negócios, toque no ícone de chamada para chamar um contato  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Transferir uma chamada  <br/> |& #x 2714;|& #x 2714;|& #x 2714;||
|Transferência consultiva  <br/> |& #x 2714; & #x 2778; ||||
|Gerenciar o encaminhamento de chamadas  <br/> |& #x 2714; & #x 2776; |& #x 2714;|& #x 2714;|& #x 2714;|
|Gerenciar configurações de chamadas de equipe  <br/> |& #x 2714; & #x 2776; ||||
|Gerenciar representantes  <br/> |& #x 2714; & #x 2776; ||||
|Iniciar uma chamada para um Grupo de Resposta  <br/> |& #x 2714; & #x 2776; ||||
|Serviços de suporte a emergências  <br/> |& #x 2714; & #x 2777; ||||
|Realizar chamadas em nome de outro contato (cenário de gerente/representante)  <br/> |& #x 2714; & #x 2776; ||||
|Lidar com chamadas de outro contato, se configurado como um delegado  <br/> |& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |& #x 2714; & #x 2776; |
|Use Telefonar via Trabalho   <br/> |& #x 2714; & #x 2776; |& #x 2714;|& #x 2714;||
|Acessar caixa postal  <br/> |& #x 2714;|& #x 2714;|& #x 2714;||
|Use o teclado no Skype para negócios  <br/> |& #x 2714; & #x 2776; |& #x 2714;|& #x 2714;||
   
 & #x 2776;  Disponível para Skype para usuários corporativos Online e/ou Office 365 E5, e os usuários hospedados no Skype para Business Server ou o Lync Server 2013 com o Enterprise Voice habilitado.
  
 & #x 2777;  Para Skype para usuários corporativos Online e/ou Office 365, este recurso é suportado por parceiros da Microsoft.
  
 & #x 2778;  Somente cliente de área de trabalho do Windows.
  
## <a name="external-user-support"></a>Suporte a usuários externos


 | Recurso/capacidade  | Skype para o cliente de desktop de negócios  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar IM com um contato público  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Iniciar IM com um contato federado  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Conduzir chamadas de duas partes com usuários externos  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Conduzir chamadas de várias partes com usuários externos  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Usar chamada via trabalho para alcançar um contato federado em seu telefone móvel chamando o seu número comercial publicado & #x 2776;            <br/> ||& #x 2714;|& #x 2714;|& #x 2714;|
   
 & #x 2776;  Por padrão, os usuários federados são atribuídos a relação de privacidade contatos externos. Para que seja possível chamar um contato federado em seu telefone celular ligando para seu número comercial publicado, o contato federado deve atribuir manualmente a você a relação de privacidade Colegas.
  
## <a name="address-book-integration"></a>Integração do catálogo de endereços


 | Recurso/capacidade  | Skype para o cliente de desktop de negócios  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Ligar para contatos do catálogo de endereços do dispositivo  <br/> ||& #x 2714;|& #x 2714;|& #x 2714;|
|Tornar Skype para chamadas de negócios para os contatos diretamente do catálogo de endereços do dispositivo  <br/> ||||& #x 2714;|
   
## <a name="archiving-and-compliance-support"></a>Suporte a arquivamento e conformidade


 | Recurso/capacidade  | Skype para o cliente de desktop de negócios  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Oferece arquivamento no lado do cliente  <br/> |& #x 2714;||||
|Oferece gravação no lado do cliente  <br/> |& #x 2714; & #x 2776; ||||
   
 & #x 2776;  Não disponível para Skype para usuários corporativos Online e/ou Office 365.
  
## <a name="modern-authentication"></a>Autenticação moderna

Essa tabela abrange os recursos que precisam de suporte à autenticação moderna.
  
Autenticação moderna também requer uma topologia descrita em [Skype para topologias de negócios compatíveis com autenticação moderno](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Recurso/funcionalidade  | Skype para o cliente de desktop de negócios  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Autenticação moderna  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Autenticação multifator  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Autenticação baseada em certificado  <br/> |& #x 2714; (apenas para domínio dispositivo)  <br/> ||& #x 2714;|& #x 2714;|
|Gerenciamento de aplicativos móveis (via Intune)  <br/> |||& #x 2714;|& #x 2714;|
   

