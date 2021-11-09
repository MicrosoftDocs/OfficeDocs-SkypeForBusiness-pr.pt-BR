---
title: Comparação de recursos do cliente móvel para Skype for Business
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Resumo: revise o suporte ao recurso para o cliente móvel enquanto planeja Skype for Business Server.'
ms.openlocfilehash: f1bbb046827ef762f5def1d532089e9621c32b28
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834119"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Comparação de recursos do cliente móvel para Skype for Business
 
**Resumo:** Revise o suporte ao recurso para o cliente móvel enquanto planeja Skype for Business Server.
  
Este artigo compara os recursos e recursos entre os clientes móveis Skype for Business o cliente Skype for Business da área de trabalho nas seguintes categorias:
  
- Entrar, notificações por push e recursos gerais
    
- Presença aprimorada
    
- Contatos e grupos de contatos
    
- Mensagens instantâneas (IM)
    
- Skype for Business para Skype for Business áudio e vídeo
    
- Conferência
    
- Telefonia
    
- Usuários externos
    
- Arquivamento e conformidade
    
-  Autenticação Moderna
    
As tabelas a seguir listam os recursos disponíveis para Skype for Business usuários em uma implantação local de Skype for Business Server. Os mesmos recursos também estão disponíveis para usuários Skype for Business Online e Microsoft 365 ou Office 365, a menos que indicado de outra forma nas notas de rodapé da tabela.
  
> [!NOTE]
> Para ajuda online e recursos para usuários finais, consulte [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Para comparar os recursos disponíveis em outros clientes Skype for Business, consulte Comparação de recursos do cliente de área de [trabalho para Skype for Business](desktop-feature-comparison.md). 

> [!NOTE]
> O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Entrar, notificações por push e recursos gerais

 
 | Recurso/funcionalidade  | Skype for Business cliente da área de trabalho  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business sessão permanece assinada  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Suporte para notificações de push  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|As informações de conta de vários usuários podem ser armazenadas em cache no mesmo dispositivo  <br/> |&#x2714;||||
|Leitor/voz de tela  <br/> |&#x2714;|&#x2714; &#x2777;           somente inglês  <br/> |&#x2714;|&#x2714;|
|Usar um teclado externo para acessibilidade  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Suporte ao Programa de Aperfeiçoamento da Experiência do Cliente da Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; No Windows Phone, Skype for Business sair automaticamente após um período de inatividade, da seguinte forma:
  
- Se o usuário habilitar notificações por push, Skype for Business sair após 10 dias de inatividade.
    
- Se o usuário não tiver habilitado notificações por push, Skype for Business sair assim que o usuário sair do aplicativo.
    
Em dispositivos iOS, Skype for Business sair automaticamente depois que o cliente móvel não entrar em contato com o servidor por 10 dias devido à perda de conectividade de rede ou outros problemas.
  
 &#x2777; somente no aplicativo.
  
 &#x2778; as notificações estão disponíveis quando o aplicativo está em execução em segundo plano.
 
 &#x2779; Google/Android/GCNS e serviços de notificação móvel Apple/APNS usam criptografia HTTPS/TLS para entrega de notificações. A carga de notificação é manipulada em texto sem texto enquanto processada pelo provedor de notificação.
 
-   Skype for Business para Android recebe notificações simples (entregues por meio do GCNS) sem dados do cliente.
-   Skype for Business para iOS recebe notificações (entregues via APNS) que podem incluir dados do cliente para a chamada ou mensagem.
 
  
## <a name="enhanced-presence-support"></a>Suporte a presença aprimorado


 | Recurso/funcionalidade  | Skype for Business cliente da área de trabalho  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publique e exiba o status  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exiba o status com base nas informações do calendário livre/ocupado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exiba as notas de status e as mensagens Fora do Escritório  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Adicione um local personalizado  <br/> |&#x2714;||||
|Adicione uma nota personalizada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Publicar status com base na informação de disponibilidade do calendário  <br/> |&#x2714; &#x2776; ||||
|Definir o estado de presença manual (como Ocupado, Não Incomodar e assim por diante)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Skype for Business clientes móveis não atualizem a presença de um usuário com base nas informações de calendário de livre/ocupado do usuário. Se um usuário do cliente móvel também estiver Skype for Business cliente da área de trabalho, o cliente da área de trabalho atualizará a presença do usuário com base nas informações de calendário de livre/ocupado do usuário. Se o usuário estiver somente com um cliente móvel, a presença do usuário não será atualizada com base nas informações do calendário de livre/ocupado.
  
## <a name="contacts-and-contact-groups-support"></a>Suporte a contatos e grupos de contatos


 | Recurso/funcionalidade  | Skype for Business cliente da área de trabalho  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Exiba a lista de Contatos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir grupos de contato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir grupos de contatos frequentes  <br/> |&#x2714;||||
|Modifique a lista de Contatos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Marque os contatos para alertas de alteração do status  <br/> |&#x2714;||||
|Controle as relações de privacidade  <br/> |&#x2714;||||
|Pesquise na agenda corporativa  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Pesquisar lista de contatos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Gerencie os grupos de contatos  <br/> |&#x2714;|||&#x2714;|
|Expandir grupos de distribuição  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Pesquise os Grupos de Respostas  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Exibir ou ocultar fotos do contato  <br/> |&#x2714;|&#x2714;|||
|Fixar um contato na tela inicial  <br/> ||&#x2714;|||
   
 &#x2776; não está disponível para Skype for Business online e/ou Microsoft 365 ou Office 365 usuários.
  
## <a name="instant-messaging-support"></a>Suporte a Mensagens Instantâneas


 | Recurso/funcionalidade  | Skype for Business cliente da área de trabalho  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar mensagens instantâneas (IM) com um contato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participe de IM com várias partes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Convidar outros por uma janela de conversa  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir conversas atuais  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navegue entre várias conversas de IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Fazer o login automaticamente de conversas de IM no Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Enviar uma conversa de IM como uma mensagem de email  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inicie um email para um contato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir convites de IM perdidos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vibrar com IM em entrada  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776; Esse dispositivo vibra sempre que um IM é recebido, mesmo que a mensagem atual na conversa de mensagens IM seja exibida
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for Business para Skype for Business áudio e vídeo


 | Recurso/funcionalidade  | Skype for Business cliente da área de trabalho  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business voz para Skype for Business voz  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for Business vídeo Skype for Business vídeo  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> O vídeo em um dispositivo móvel exige uma conexão WiFi por padrão. 
  
## <a name="conferencing-support"></a>Suporte a conferência


 | Recurso/funcionalidade  | Skype for Business cliente da área de trabalho  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Clique em um link no lembrete de reunião para participar de um vídeo ou reunião voIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participe de IM com várias partes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar a conferência discada (o servidor chama o dispositivo móvel)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Use a conferência discada de áudio  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir vídeo da reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir vídeo de várias partes (modo de exibição de galeria)  <br/> |&#x2714;||||
|Aguardar no lobby da reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Use controles de apresentador durante a reunião  <br/> |&#x2714;||||
|Acessar lista de participação da reunião detalhada para conferências de áudio  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Acessar lista de participação da reunião detalhada para conferências de IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Compartilhar área de trabalho ou programa  <br/> |&#x2714;||||
|Exibir área de trabalho ou programa compartilhado (VbSS ou RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Exibir arquivos PowerPoint compartilhados  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|Upload e apresentar PowerPoint arquivos  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Usar ferramentas de reunião (usar quadro de comunicação, realizar pesquisas, compartilhar arquivos)  <br/> |&#x2714;||||
|Navegar por uma lista de suas reuniões  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participe de uma reunião mesmo que você não tenha uma Skype for Business de usuário  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir mais informações sobre participantes da reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar uma conversa de grupo não agendada com vários participantes diretamente do seu cliente ou dispositivo  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; Para Microsoft 365 ou Office 365, esse recurso requer Enterprise Voice, que faz parte da licença do E5.
  
 &#x2777; requer uma conexão WiFi por padrão.
 
 &#x2778; não há suporte para visualizar vídeo incorporado PowerPoint apresentações.
  
## <a name="telephony-support"></a>Suporte a telefonia


 | Recurso/funcionalidade  | Skype for Business cliente da área de trabalho  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Em Skype for Business, toque no ícone de chamada para chamar um contato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transferir uma chamada  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Transferência Consultiva  <br/> |&#x2714; &#x2778; ||||
|Gerencie o redirecionamento de chamada  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Gerenciamento de configurações de chamada em equipe  <br/> |&#x2714; &#x2776; ||||
|Gerenciamento de delegados  <br/> |&#x2714; &#x2776; ||||
|Iniciação de uma chamada para um Grupo de Resposta  <br/> |&#x2714; &#x2776; ||||
|Serviços de suporte a emergências  <br/> |&#x2714; &#x2777; ||||
|Realização de chamadas em nome de outro contato (cenário gerente/delegado)  <br/> |&#x2714; &#x2776; ||||
|Manipular chamadas de outro contato, se configuradas como delegados  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Usar Chamada via Trabalho  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Acessar a caixa postal  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Use o teclado no Skype for Business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; Disponível para usuários do Skype for Business Online e/ou Office 365 E5 e usuários do Skype for Business Server ou Lync Server 2013 com Enterprise Voice habilitados.
  
 &#x2777; para usuários Skype for Business Online e/ou Microsoft 365 ou Office 365, esse recurso é suportado por parceiros da Microsoft.
  
 &#x2778; Windows somente cliente desktop.
  
## <a name="external-user-support"></a>Suporte a usuários externos


 | Recurso/funcionalidade  | Skype for Business cliente da área de trabalho  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar o IM com um contato público  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar o IM com um contato federado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Conduzir chamadas de duas partes com usuários externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Conduzir chamadas de várias partes com usuários externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Use Call via Work para alcançar um contato federado em seu telefone celular chamando seu número de trabalho publicado &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Por padrão, os usuários federados são atribuídos à relação de privacidade contatos externos. Para poder alcançar um contato federado em seu telefone celular chamando seu número de trabalho publicado, o contato federado deve atribuir manualmente a você a relação de privacidade Colegas.
  
## <a name="address-book-integration"></a>Integração do livro de endereços


 | Recurso/funcionalidade  | Skype for Business cliente da área de trabalho  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Chamar contatos do agendamento de endereços do dispositivo  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Fazer Skype for Business para contatos diretamente do livro de endereços do dispositivo  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Suporte a arquivamento e conformidade


 | Recurso/funcionalidade  | Skype for Business cliente da área de trabalho  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Forneça arquivamento no lado do cliente  <br/> |&#x2714;||||
|Forneça gravação no lado do cliente  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; não está disponível para Skype for Business online e/ou Microsoft 365 ou Office 365 usuários.
  
## <a name="modern-authentication"></a>Autenticação Moderna

Esta tabela aborda recursos que exigem suporte para autenticação moderna.
  
A autenticação moderna também requer uma topologia descrita [em Skype for Business topologias com suporte com Autenticação Moderna](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Recurso/funcionalidade  | Skype for Business cliente da área de trabalho  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Autenticação Moderna  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticação multifafação  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticação baseada em certificado  <br/> |&#x2714;(Somente dispositivo ingressado em domínio)  <br/> ||&#x2714;|&#x2714;|
|Gerenciamento de aplicativo móvel (via Intune)  <br/> |||&#x2714;|&#x2714;|
   

