---
title: Comparação de recursos do cliente móvel para o Skype for Business
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Resumo: revise o suporte ao recurso para o cliente móvel durante o planejamento do Skype for Business Server.'
ms.openlocfilehash: 36ae93e796e4142a9ae3b5fb85ac806c9a38cdca
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777766"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Comparação de recursos do cliente móvel para o Skype for Business
 
**Resumo:** Revise o suporte ao recurso para o cliente móvel durante o planejamento do Skype for Business Server.
  
Este artigo compara os recursos e os recursos entre os clientes móveis do Skype for Business e o cliente de área de trabalho do Skype for Business nas seguintes categorias:
  
- Login, notificações por push e recursos gerais
    
- Presença aprimorada
    
- Contatos e grupos de contatos
    
- Mensagens instantâneas (IM)
    
- Skype for Business para áudio e vídeo do Skype for Business
    
- Conferências
    
- Telefonia
    
- Usuários externos
    
- Arquivamento e conformidade
    
-  Autenticação moderna
    
As tabelas a seguir listam os recursos disponíveis para os usuários do Skype for Business em uma implantação local do Skype for Business Server. Os mesmos recursos também estão disponíveis para os usuários do Skype for Business Online e do Microsoft 365 ou do Office 365, a menos que indicado de outra forma nas notas de rodapé da tabela.
  
> [!NOTE]
> Para obter ajuda online e recursos para usuários finais, consulte [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Para comparar os recursos disponíveis em outros clientes do Skype for Business, consulte [comparação de recursos do cliente de desktop para o Skype for Business](desktop-feature-comparison.md). 

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para suportar mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Login, notificações por push e recursos gerais

 
 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|A sessão do Skype for Business permanece conectada  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Suporte para notificações de push  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|As informações de conta de vários usuários podem ser armazenadas em cache no mesmo dispositivo  <br/> |&#x2714;||||
|Leitor de tela/voz sobre  <br/> |&#x2714;|Somente em inglês &#x2714; &#x2777;   <br/> |&#x2714;|&#x2714;|
|Usar um teclado externo para acessibilidade  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Suporte ao programa de aperfeiçoamento da experiência do usuário da Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; no Windows Phone, o Skype for Business se desconecta automaticamente após um período de inatividade, da seguinte maneira:
  
- Se o usuário tiver habilitado as notificações por push, o Skype for Business se inscreverá após 10 dias de inatividade.
    
- Se o usuário não habilitou notificações por push, o Skype for Business se inscreverá assim que o usuário sair do aplicativo.
    
Nos dispositivos iOS, o Skype for Business se desconecta automaticamente depois que o cliente móvel não entrou no servidor por 10 dias devido à perda da conectividade de rede ou de outros problemas.
  
 &#x2777; somente no aplicativo.
  
 &#x2778; notificações estão disponíveis quando o aplicativo é executado em segundo plano.
 
 &#x2779; o Google/Android/GCNS e os serviços de notificação de celular de Apple/APNS usam criptografia HTTPS/TLS para a entrega de notificações. A carga de notificação é tratada em texto sem formatação enquanto processada pelo provedor de notificações.
 
-   O Skype for Business para Android recebe notificações simples (entregues via GCNS) sem dados do cliente.
-   O Skype for Business para iOS recebe notificações (entregues via APNS), que podem incluir dados do cliente para a chamada ou a mensagem.
 
  
## <a name="enhanced-presence-support"></a>Suporte de presença avançada


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publique e exiba o status  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exiba o status com base nas informações do calendário livre/ocupado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exiba as notas de status e as mensagens Fora do Escritório  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Adicione um local personalizado  <br/> |&#x2714;||||
|Adicione uma nota personalizada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Publicar status com base na informação de disponibilidade do calendário  <br/> |&#x2714; &#x2776; ||||
|Definir o estado de presença manual (como ocupado, não incomodar e assim por diante)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; clientes móveis do Skype for Business não atualizam a presença de um usuário com base nas informações do calendário de disponibilidade do usuário. Se um usuário de cliente móvel também estiver conectado ao cliente de desktop do Skype for Business, o cliente da área de trabalho atualizará a presença do usuário com base nas informações do calendário de disponibilidade do usuário. Se o usuário estiver conectado somente a um cliente móvel, a presença do usuário não será atualizada com base nas informações do calendário de disponibilidade.
  
## <a name="contacts-and-contact-groups-support"></a>Suporte para contatos e grupos de contatos


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
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
|Expanda os grupos de distribuição  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Pesquise os Grupos de Respostas  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Exibir ou ocultar fotos do contato  <br/> |&#x2714;|&#x2714;|||
|Fixar um contato na sua tela inicial  <br/> ||&#x2714;|||
   
 &#x2776; não está disponível para usuários do Skype for Business Online e/ou Microsoft 365 ou do Office 365.
  
## <a name="instant-messaging-support"></a>Suporte a mensagens instantâneas


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
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
   
 &#x2776; este dispositivo vibra cada vez que um IM é recebido, mesmo que a mensagem atual na conversa de mensagens instantâneas seja exibida
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for Business para áudio e vídeo do Skype for Business


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business-to-Skype for Business Voice  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vídeo do Skype for Business para o Skype for Business  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> O vídeo em um dispositivo móvel requer uma conexão WiFi por padrão. 
  
## <a name="conferencing-support"></a>Suporte de conferência


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Clique em um link no lembrete de reunião para ingressar em uma reunião de vídeo ou VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participe de IM com várias partes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar a conferência discada (o servidor chama o dispositivo móvel)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Use a conferência discada de áudio  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir vídeo da reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir vídeo de vários participantes (modo de exibição de galeria)  <br/> |&#x2714;||||
|Aguardar no lobby da reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Use controles de apresentador durante a reunião  <br/> |&#x2714;||||
|Acessar lista de participação da reunião detalhada para conferências de áudio  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Acessar lista de participação da reunião detalhada para conferências de IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Compartilhar área de trabalho ou programa  <br/> |&#x2714;||||
|Exibir a área de trabalho compartilhada ou programa (VbSS ou RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Exibir arquivos compartilhados do PowerPoint  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|Carregar e apresentar arquivos do PowerPoint  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Usar ferramentas de reunião (usar quadro de comunicações, realizar pesquisas, compartilhar arquivos)  <br/> |&#x2714;||||
|Navegar por uma lista de suas reuniões  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar de uma reunião mesmo que você não tenha uma conta do Skype for Business  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Exibir mais informações sobre participantes da reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar uma conversa de grupo não agendada com vários participantes diretamente de seu cliente ou dispositivo  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; para usuários do Microsoft 365 ou do Office 365, este recurso exige o Enterprise Voice, que é parte da licença e5.
  
 O &#x2777; requer uma conexão WiFi por padrão.
 
 &#x2778; não há suporte para a exibição de vídeo incorporado em apresentações do PowerPoint.
  
## <a name="telephony-support"></a>Suporte para telefonia


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|No Skype for Business, toque no ícone de chamada para ligar para um contato  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transferir uma chamada  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Transferência consultiva  <br/> |&#x2714; &#x2778; ||||
|Gerencie o redirecionamento de chamada  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Gerenciamento de configurações de chamada em equipe  <br/> |&#x2714; &#x2776; ||||
|Gerenciamento de delegados  <br/> |&#x2714; &#x2776; ||||
|Iniciação de uma chamada para um Grupo de Resposta  <br/> |&#x2714; &#x2776; ||||
|Serviços de suporte a emergências  <br/> |&#x2714; &#x2777; ||||
|Realização de chamadas em nome de outro contato (cenário gerente/delegado)  <br/> |&#x2714; &#x2776; ||||
|Lidar com as chamadas de outro contato, se configurado como um representante  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Usar a chamada via trabalho  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Acessar a caixa postal  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Usar o teclado no Skype for Business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; disponível para os usuários do Skype for Business Online e/ou Office 365 E5 e usuários hospedados no Skype for Business Server ou no Lync Server 2013 com o Enterprise Voice habilitado.
  
 &#x2777; para usuários do Skype for Business Online e/ou Microsoft 365 ou do Office 365, esse recurso tem suporte dos parceiros da Microsoft.
  
 &#x2778; somente cliente da área de trabalho do Windows.
  
## <a name="external-user-support"></a>Suporte a usuários externos


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar o IM com um contato público  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Iniciar o IM com um contato federado  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Conduzir chamadas de duas partes com usuários externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Conduzir chamadas de várias partes com usuários externos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar a chamada via trabalho para acessar um contato federado em seu telefone celular chamando seu número de trabalho publicado &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; por padrão, os usuários federados recebem a relação de privacidade contatos externos. Para poder acessar um contato federado em seu celular chamando o número de trabalho publicado, o contato federado deve atribuir manualmente o relacionamento de privacidade de colegas.
  
## <a name="address-book-integration"></a>Integração do catálogo de endereços


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Contatos do catálogo de endereços do dispositivo de chamada  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Fazer chamadas do Skype for Business para contatos diretamente do catálogo de endereços do dispositivo  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Suporte para arquivamento e conformidade


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Forneça arquivamento no lado do cliente  <br/> |&#x2714;||||
|Forneça gravação no lado do cliente  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; não está disponível para usuários do Skype for Business Online e/ou Microsoft 365 ou do Office 365.
  
## <a name="modern-authentication"></a>Autenticação moderna

Esta tabela abrange os recursos que exigem suporte para a autenticação moderna.
  
A autenticação moderna também requer uma topologia descrita nas [topologias do Skype for Business compatíveis com a autenticação moderna](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Autenticação moderna  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticação multifator  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Autenticação baseada em certificado  <br/> |&#x2714; (somente dispositivo ingresso no domínio)  <br/> ||&#x2714;|&#x2714;|
|Gerenciamento de aplicativo móvel (via Intune)  <br/> |||&#x2714;|&#x2714;|
   

