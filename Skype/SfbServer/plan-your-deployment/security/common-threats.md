---
title: Ameaças comuns à segurança na computação moderna
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/22/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
description: Como Skype for Business Server é um sistema de comunicações de classe empresarial, você deve estar ciente de ataques comuns de segurança que podem afetar sua infraestrutura e comunicações.
ms.openlocfilehash: dcc889ea43c06c2f8166d588b8d7e5eb7075b52c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741917"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Ameaças comuns à segurança na computação moderna
 
Como Skype for Business Server é um sistema de comunicações de classe empresarial, você deve estar ciente de ataques comuns de segurança que podem afetar sua infraestrutura e comunicações.
  
## <a name="compromised-key-attack"></a>Ataque de chave comprometida

Uma chave é um número ou código secreto usado para criptografar, descriptografar ou validar informações secretas. Há duas chaves confidenciais em uso na PKI (infraestrutura de chave pública) que devem ser consideradas: 
  
- A chave privada que cada titular de certificado tem
    
- A chave de sessão usada após uma identificação bem-sucedida e troca de chave de sessão pelos parceiros de comunicação
    
Um ataque de chave comprometida ocorre quando o invasor determina a chave privada ou a chave de sessão. Quando o invasor consegue determinar a chave, ele pode usar a chave para descriptografar os dados criptografados sem o conhecimento do remetente.
  
Skype for Business Server usa os recursos PKI no sistema operacional Windows Server para proteger os dados principais usados para criptografia para as conexões TLS (Transport Layer Security). As chaves usadas para criptografia de mídia são trocadas por conexões TLS.
  
## <a name="network-denial-of-service-attack"></a>Ataque de negação de serviço da rede

O ataque de negação de serviço ocorre quando o invasor impede a operação e o uso normal da rede pelos usuários válidos. Isso é feito quando o invasor inunda o serviço com solicitações legítimas que sobrecarregam o uso do serviço por usuários legítimos. Usando um ataque de negação de serviço, o invasor pode fazer o seguinte:
  
- Enviar dados inválidos a aplicativos e serviços em execução na rede atacada para interromper seu funcionamento normal.
    
- Enviar um grande volume de tráfego, sobrecarregando o sistema até que ele pare de responder ou responda lentamente às solicitações legítimas.
    
- Ocultar a evidência dos ataques.
    
- Impedir que os usuários acessem os recursos da rede.
    
## <a name="eavesdropping-sniffing-snooping"></a>Eavesdropping (Sniffing, Snooping)

A escuta pode ocorrer quando um invasor obtém acesso ao caminho de dados em uma rede e tem a capacidade de monitorar e ler o tráfego. Isso também é chamado de farejamento ou snooping. Se o tráfego estiver em texto sem texto, o invasor poderá ler o tráfego quando o invasor tiver acesso ao caminho. Um exemplo é um ataque executado controlando um roteador no caminho dos dados. 
  
A recomendação padrão e a configuração para o tráfego dentro Skype for Business Server é usar TLS mútuo (MTLS) entre servidores confiáveis e TLS de cliente para servidor. Essa medida de proteção torna um ataque muito difícil ou impossível de ser alcançado dentro do período de tempo em que uma determinada conversa ocorre. O TLS autentica todos os participantes e criptografa todo o tráfego. Isso não impede a escuta, mas o invasor não pode ler o tráfego, a menos que a criptografia seja quebrada.
  
O protocolo NAT de retransmissão de retransmissão (TURN) não ordena que o tráfego seja criptografado e as informações que ele está enviando são protegidas pela integridade da mensagem. Embora ele seja aberto à escuta, as informações que ele está enviando (ou seja, os endereços IP e a porta) podem ser extraídas diretamente, bastando olhar para os endereços de origem e de destino dos pacotes. O serviço de Borda A/V garante que os dados são válidos verificando a Integridade da Mensagem da mensagem usando a chave derivada de alguns itens, incluindo uma senha TURN, que nunca é enviada em texto claro. Se o SrTP (Protocolo de Tempo Real Seguro) for usado, o tráfego de mídia também será criptografado.
  
## <a name="identity-spoofing-ip-address-and-caller-id-spoofing"></a>Identidade Spoofing (Endereço IP e ID do Chamador Spoofing)

A Spoofing de Identidade ocorre quando o invasor determina e usa um número de telefone de um usuário válido (id do chamador) ou um endereço IP de uma rede, computador ou componente de rede sem autorização para fazer isso. Um ataque bem-sucedido permite que o invasor opere como se o invasor fosse a entidade normalmente identificada pelo número de telefone (id do chamador) ou o endereço IP.

No contexto de Skype for Business Server, a Spoofing de Endereço IP só entra em jogo se um administrador tiver feito os dois seguintes:
  
- Configurou conexões que suportam apenas TCP (Protocolo de Controle de Transmissão) (não é recomendado porque as comunicações TCP não são criptografadas).
    
- Marcou os endereços IPs das conexões como hosts confiáveis.
    
Este é menos um problema para conexões TLS (Transport Layer Security), porque a TLS autentica todas as partes e criptografa todo o tráfego. Usar o TLS evita que um invasor realize falsificação de endereço IP em uma determinada conexão (por exemplo, conexões TLS mútuas). No entanto, um invasor ainda pode fazer uma cópia do endereço do servidor DNS que Skype for Business Server usa. No entanto, como a autenticação no Skype for Business é realizada com certificados, um invasor não teria um certificado válido necessário para fazer a spoof de uma das partes na comunicação.

Por outro lado, a Spoofing de Id do Chamador entra em jogo quando você estabelece um tronco SIP entre um provedor, um gateway PSTN ou outro sistema PBX e Skype for Business Server. Nesses casos, Skype for Business Server oferece nenhuma proteção para evitar a fraude de ID do chamador. Isso significa que um usuário Skype for Business pode receber uma chamada do tronco SIP com uma ID de chamador falso exibindo o número de telefone ou o nome de exibição (se a pesquisa de número reverso se aplicar) de outro usuário Skype for Business. A proteção a isso deve ser aplicada no lado do provedor, PSTN ou gateway PBX.
  
## <a name="man-in-the-middle-attack"></a>Ataque de interceptação

Um ataque man-in-the-middle ocorre quando um invasor redireciona a comunicação entre dois usuários por meio do computador do invasor sem o conhecimento dos dois usuários que se comunicam. O invasor pode monitorar e ler o tráfego antes de enviá-lo para o destinatário pretendido. Cada usuário na comunicação envia tráfego sem saber e recebe tráfego do invasor, tudo pensando que está se comunicando apenas com o usuário pretendido. Isso pode acontecer se um invasor puder modificar os Serviços de Domínio do Active Directory para adicionar seu servidor como um servidor confiável ou modificar o DNS (Sistema de Nomes de Domínio) para fazer com que os clientes se conectem por meio do invasor no caminho para o servidor. Um ataque man-in-the-middle também pode ocorrer com o tráfego de mídia entre dois clientes. No entanto, Skype for Business Server áudio ponto a ponto, vídeo e compartilhamento de aplicativos, os fluxos são criptografados com SRTP, usando chaves criptográficas que são negociadas entre os pares que estão usando o Protocolo de Iniciação de Sessão (SIP) por TLS. Servidores como Chat de Grupo usam HTTPS para melhorar a segurança do tráfego web.
  
## <a name="rtp-replay-attack"></a>Ataque de repetição ao RTP

Um ataque de repetição ocorre quando uma transmissão de mídia válida entre duas partes é interceptada e retransmitida para fins mal-intencionados. O SRTP usado em conjunto com um protocolo de sinalização seguro protege as transmissões contra ataques de repetição habilitando o receptor a manter um índice de pacotes RTP já recebidos e a comparar cada novo pacote com os já listados no índice.
  
## <a name="spim"></a>Spim

Spim são mensagens instantâneas comerciais não solicitadas ou solicitações de inscrição de presença. Embora não seja propriamente um compromisso da rede, essa situação é, no mínimo, irritante, pode reduzir a disponibilidade de recursos e a produção e possivelmente comprometerá a rede. Um exemplo disso são os usuários que repassam spims entre si ao enviar solicitações. Os usuários podem bloquear uns aos outros para evitar que isso aconteça, mas com a federação, se um ataque de spim coordenado for estabelecido, possivelmente será difícil contornar o problema, a menos que você desabilite a federação do parceiro.
  
## <a name="viruses-and-worms"></a>Vírus e Worms

Um vírus é uma unidade de código cujo objetivo é reproduzir unidades de código adicionais semelhantes. Para funcionar, um vírus precisa de um host, como um arquivo, email ou programa. A verme é uma unidade de código cujo objetivo é reproduzir unidades de código adicionais e semelhantes, mas não precisa de um host. Vírus e worms aparecem principalmente durante transferências de arquivos entre clientes ou quando URLs são enviadas de outros usuários. Se um vírus estiver em seu computador, ele poderá, por exemplo, usar sua identidade e enviar mensagens instantâneas em seu nome.
  
## <a name="personally-identifiable-information"></a>Informações de identificação pessoal

Skype for Business Server tem o potencial de divulgar informações por meio de uma rede pública que pode ser vinculada a um indivíduo. Os tipos de informações podem ser classificados em duas categorias específicas:
  
- **Dados de presença aprimorados** Dados de presença aprimorados são informações que um usuário pode optar por compartilhar ou não compartilhar por meio de um link para um parceiro federado ou com contatos dentro de uma organização. Esses dados não são compartilhados com usuários em uma rede pública de mensagens instantâneas. As políticas cliente e outras configurações cliente podem aplicar algum controle com o administrador do sistema. No Skype for Business Server, o modo de privacidade de presença aprimorado pode ser configurado para um usuário individual para impedir que Skype for Business usuários que não estão na lista de Contatos do usuário possam ver as informações de presença do usuário. O modo de privacidade de presença aprimorado não impede que os usuários do Microsoft Office Communicator 2007 e Microsoft Office Communicator 2007 R2 veja as informações de presença de um usuário. Para obter detalhes sobre como implantar o cliente e a presença, consulte [Deploy clients for Skype for Business Server](../../deploy/deploy-clients/deploy-clients.md) and Plan for instant [messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
    
- **Dados obrigatórios** Os dados obrigatórios são necessários para a operação adequada do servidor ou do cliente e NÃO estão sob o controle da administração do cliente ou do sistema. Essas são as informações necessárias em um nível de servidor ou de rede para fins de roteamento, manutenção de estado e sinalização.
    
As tabelas a seguir listam os dados expostos em uma rede pública.
  
**Dados de presença aprimorados**

|**Dados Divulgados**|**Possível Configurações**|
|:-----|:-----|
|Dados pessoais  <br/> |Nome, Título, Empresa, Endereço de Email, Fuso Horário  <br/> |
|Números de telefone  <br/> |Comercial, Celular, Residencial  <br/> |
|Informações do calendário  <br/> |Aviso gratuito/ocupado, Aviso de Saída, Detalhes da Reunião (para aqueles que têm acesso ao calendário)  <br/> |
|Status de presença  <br/> |Ausente, Disponível, Ocupado, Não Incomodar, Offline  <br/> |
   
**Dados obrigatórios**


| **Dados Divulgados** | **Informações de exemplo**                            |
|:-------------------|:---------------------------------------------------|
| Endereço IP  <br/>  | Endereço real do computador ou endereço NAT  <br/> |
| SIP URI  <br/>     | jeremylos@litwareinc.com  <br/>                    |

