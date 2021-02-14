---
title: Planejar serviços de emergência no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: Saiba mais sobre os serviços do Enhanced 9-1-1 (E9-1-1) no Skype for Business Server Enterprise Voice, incluindo aquisição de local e roteamento de chamadas.
ms.openlocfilehash: e8eb805a4e4d55f08a4c6aec1a57618c74bcfa02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825761"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Planejar serviços de emergência no Skype for Business Server

Saiba mais sobre os serviços do Enhanced 9-1-1 (E9-1-1) no Skype for Business Server Enterprise Voice, incluindo aquisição de local e roteamento de chamadas.

O Skype for Business Server oferece suporte a serviços do Enhanced 9-1-1 (E9-1-1) nos Estados Unidos como parte de uma implantação do Enterprise Voice. O E9-1-1 é um recurso de expedição de emergência que associa uma chamada 9-1-1 a um ERL (Local de Resposta a Emergência) que consiste em endereços residenciais (ou seja, rua) e outras informações de local mais específicas, como números de piso, para chamadas de edifícios de escritórios e outras instalações multi-locações. Usando a ERL fornecida, um PSAP (Ponto de Atendimento de Segurança Pública) pode expedir imediatamente os primeiros respondentes para o chamador com problemas com risco reduzido de direcionar inadvertidamente o respondente para um local incorreto ou ambíguo.

> [!NOTE]
> O Skype for Business Server agora dá suporte à configuração de vários números de emergência para um cliente. Para obter mais informações, [consulte Plano para vários números de emergência no Skype for Business Server.](multiple-emergency-numbers.md)

> [!NOTE]
> O Skype for Business Server tem três recursos avançados do Enterprise Voice: controle de admissão de chamadas, serviços de emergência (E9-1-1) e bypass de mídia. Para obter uma visão geral das informações de planejamento que são comuns a todos esses três recursos, consulte Configurações de rede para os recursos avançados do Enterprise Voice no [Skype for Business Server.](network-settings-for-advanced-features.md)

O Skype for Business Server dá suporte à chamada E9-1-1 (Enhanced 9-1-1) de clientes do Skype for Business e dispositivos Lync Phone Edition. Quando você configura o Skype for Business Server para E9-1-1, as chamadas de emergência feitas do Skype for Business ou do Lync Phone Edition incluem informações de Local de Resposta a Emergência (ERL) do banco de dados do serviço de Informações de Local. ERLs são compostos por endereços cívicos (rua) e outras informações que ajudam a identificar um local mais preciso em escritórios em edifícios e em outras instalações com vários locatários. Quando um usuário faz uma chamada de emergência, o Skype for Business Server encaminha o áudio da chamada, juntamente com as informações de local e retorno de chamada, por meio de um Servidor de Mediação para um provedor de serviços E9-1-1. O provedor de serviço E9-1-1 usa o endereço cívico do chamador para encaminhar a chamada ao PSAP (Ponto de atendimento público seguro) que atende ao local do chamador e envia também uma ESQK (Chave de consulta de serviço de emergência) que o PSAP usa para procurar o ERL do chamador.

O Skype for Business Server oferece suporte a dois métodos para rotear chamadas de emergência para um provedor de serviços E9-1-1:

- Uma conexão de tronco SIP com um provedor de serviço qualificado E9-1-1

- Um gateway ELIN (para um provedor de serviço E9-1-1 baseado em PSTN (Rede Telefônica Pública Comutada)

Quando você usa um provedor de serviços E9-1-1 de tronco SIP, adiciona ERLs ao banco de dados de serviço de Informações de Local e valida os locais com base em um MSAG (Guia Mestre de Endereços de Rua) mantido pelo provedor de serviços E9-1-1. Se um provedor de serviços E9-1-1 receber uma chamada que não tenha informações de local ou com um local que não tenha sido validado com o MSAG, o provedor de serviços E9-1-1 roteia a chamada para um ECRC (Centro de Resposta a Chamada de Emergência) nacional/regional, que conta com funcionários especialmente treinados que obtém verbalmente o local do chamador, se possível, e encaminha manualmente a chamada para o PSAP apropriado. (Alguns provedores de serviço E9-1-1 de tronco SIP também fornecem aos clientes um DID (discagem direta interna) de PSTN ao ECRC, o que proporciona um meio alternativo de encaminhar as chamadas de 9-1-1, se um tronco SIP falhar por qualquer motivo).

Diferentemente dos telefones TDM (multiplexação de divisão de tempo) e PBX (private branch exchange) baseados em IP, que têm locais fixos, um ponto de extremidade do Skype for Business pode ser muito móvel. Quando você implanta o recurso E9-1-1, o Skype for Business Server ajuda a garantir que, independentemente de onde um chamador está localizado, a chamada de emergência pode ser roteada para o PSAP que atende ao local do chamador. Por exemplo, se o escritório principal de um usuário está localizado em Redmond, Washington, mas o usuário faz uma chamada de emergência a partir de um computador em uma filial em W main, Nona, o tronco SIP ou o provedor de serviços E9-1-1 baseado em PSTN encaminhará a chamada para o PSAP em W website, e não para o PSAP em Redmond.

Ao usar um gateway ELIN, você também adiciona ERLs ao banco de dados do serviço de Informações de Local, mas também inclui um número ELIN para cada local. O número ELIN se torna o número de discagem de emergência durante a chamada de emergência. Em seguida, é necessário certificar-se de que a operadora PSTN carrega os ELINs no banco de dados de ALI (Identificação automática de local).

> [!NOTE]
> Os dispositivos analógicos conectados ao Skype for Business não podem receber informações de localização do serviço de Informações de Local ou transmitir o local para o provedor de serviços E9-1-1.

 Se você usar a opção do provedor de serviço E9-1-1 do tronco SIP e precisar oferecer suporte ao E9-1-1 a partir de telefones analógicos, terá duas opções:

- **Opção PS-ALI tradicional** Se você tiver gateways PSTN locais em cada local onde os telefones analógicos são implantados e cada telefone analógico tiver um DID, poderá provisionar o local do dispositivo analógico diretamente com um provedor de serviços PS-ALI (Private Switch/Automatic Location Identification). Nesse caso, você configura políticas de voz do Skype for Business especialmente elaboradas e as atribui aos objetos de contato do dispositivo analógico para que as chamadas E9-1-1 desses telefones roteiem diretamente pelo gateway local para o provedor PSTN que presta serviços ao site (em vez de rotear a chamada para um tronco SIP do provedor de serviços E9-1-1). Quando uma chamada de emergência é feita, um banco de dados em um provedor PS-ALI associado ao tronco do PSTN mapeia o DID de cada telefone analógico para um local físico e fornece esse local ao PSAP. Esses registros precisam ser atualizados com o provedor de serviço PS-ALI sempre que os telefones são movidos para ERLs diferentes.

- **Opção de provedor de serviços E9-1-1** Você pode registrar os DIDs de telefone analógico e seus ERLs correspondentes com o provedor de serviços E9-1-1, se isso for suportado pelo provedor de serviços E9-1-1. Se o provedor receber uma chamada do Skype for Business Server que não inclua dados de PIDF-LO, o provedor poderá ver se há uma combinação de banco de dados no número DID do chamador. Usando o ERL recuperado de seu banco de dados, o provedor pode rotear automaticamente a chamada de emergência para o PSAP correto, e o PSAP receberá o DID do dispositivo analógico e um registro ESQK que permite ao dispatcher procurar o local do chamador.

Se você usar a opção de gateway ELIN e precisar oferecer suporte a E9-1-1 de telefones analógicos, é possível prover o local do dispositivo analógico diretamente com o provedor de serviços PS-ALI, como descrito na primeira opção acima.

De uma perspectiva do Skype for Business Server, o processo E9-1-1 pode ser separado em dois estágios:

- Estágio 1: adquirindo um local

- Estágio 2: roteando a chamada de emergência para um provedor de serviço E9-1-1

Esta seção descreve como esses estágios funcionam.

Se você planeja configurar sua infraestrutura para detectar automaticamente o local do cliente, primeiro você precisa decidir quais elementos de rede serão usados para mapear os chamadores aos locais. Para obter detalhes sobre as opções possíveis, consulte [Definir os elementos de rede usados para determinar o local no Skype for Business Server.](network-location.md)

## <a name="acquiring-a-location"></a>Adquirindo um local

Em uma implantação do Skype for Business Server E9-1-1, cada cliente do Skype for Business ou do Lync Phone Edition conectado internamente adquire ativamente seu próprio local. Após o registro SIP, o cliente fornece todas as informações de conectividade de rede que conhece em uma solicitação de local para o serviço informações de local, que é um serviço Web com suporte em um banco de dados do SQL Server replicado. Cada pool de sites centrais tem um serviço de Informações de Local, que usa as informações de rede para consultar seus registros para um local correspondente. Se houver uma combinação, o serviço de Informações de Local retornará um local para o cliente. Se não houver uma correspondentes, pode ser solicitado que o usuário insira uma localização manualmente (dependendo das definições da política de localização). Os dados de localização são transmitidos de volta para o cliente em um formato XML padronizado da IETF (Internet Engineering Task Force) chamado de PIDF-LO (Objeto de Local de Formato de Dados de Informação de Presença).

O cliente Skype for Business inclui os dados de PIDF-LO como parte de uma chamada de emergência, e esses dados são usados pelo provedor de serviços E9-1-1 para determinar o PSAP apropriado e rotear a chamada para esse PSAP junto com o ESQK correto, que permite que o dispatcher PSAP obtenha o local do chamador.

O diagrama a seguir mostra como um cliente Skype for Business adquire um local (exceto para o método de local baseado em endereço MAC do cliente de terceiros):

![Como o cliente adquire um diagrama de localização](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Para um cliente adquirir uma localização, as seguintes etapas devem ser executadas:

1. O administrador preenche o banco de dados do serviço de Informações de Local com o mapa de transmissão de rede (tabelas que mapeiam vários tipos de endereços de rede para ERLs (Locais de Resposta a Emergência) correspondentes.

2. Se você usar um provedor de serviço E9-1-1 por tronco SIP, o administrador validará as partes do endereço residencial dos ERLs com um banco de dados MSAG (Guia principal de endereços de ruas) mantido pelo provedor de serviço E9-1-1. Se você usar um gateway ELIN, o administrador garantirá que a operadora da PSTN carregue os ELINs no banco de dados ALI (Identificação de local automática).

3. Durante o registro ou sempre que ocorre uma alteração de rede, um cliente conectado internamente envia uma solicitação de local que contém os endereços de rede descobertos do cliente para o serviço de Informações de Local.

4. O serviço de Informações de Local consulta seus registros publicados em busca de um local e, se uma combinação for encontrada, retorna o ERL para o cliente no formato PIDF-LO.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Roteamento de chamadas E9-1-1 usando um tronco SIP

Usar um tronco SIP para conectar-se a um provedor de serviço E9-1-1 qualificado é uma maneira que pode ser usada para implantar o E9-1-1. Para obter detalhes sobre o uso de um gateway ELIN para conectar-se a um provedor de serviço E9-1-1 baseado na PSTN (rede telefônica pública comutada), consulte [Routing E9-1-1 Calls by Using an ELIN Gateway](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).

O diagrama a seguir mostra como uma chamada de emergência é roteada do Skype for Business Server para o PSAP (Ponto de Atendimento Público Seguro) quando você usa um tronco SIP e um provedor de serviços E9-1-1 qualificado.

**Encaminhando chamadas do E9-1-1 por meio de um tronco SIP**

![Roteamento de Chamadas de Emergência do Lync Server para pSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Quando uma chamada de emergência é feita de um cliente compatível do Skype for Business Server:

1. Um SIP INVITE que contém o local, o número de retorno de chamada do chamador e a URL de notificação (opcional) e o número de retorno de chamada de conferência são roteados para o Skype for Business Server.

2. O Skype for Business Server corresponde ao número de emergência e encaminha a chamada (com base no valor de Uso de **PSTN** definido na política de local aplicável) para um Servidor de Mediação e, a partir daí, por um tronco SIP para o provedor de serviços E9-1-1.

3. O provedor de serviços E9-1-1 encaminha as chamadas de emergência para o PSAP correto com base na localização que é fornecida com a chamada. Quando o cliente inclui um ERL (Local da resposta de emergência) com a chamada de emergência, o provedor automaticamente encaminha a chamada para o PSAP apropriado. Se a localização foi inserida manualmente pelo usuário, o ECRC (Centro de resposta de chamada de emergência) primeiro verifica verbalmente a precisão da localização com o chamador antes do encaminhamento da chamada de emergência para o PSAP.

4. Se você configurou a política de local para notificações, um ou mais funcionários de segurança da sua organização receberão uma mensagem instantânea especial de notificação de emergência do Skype for Business. Essa mensagem sempre aparece nas telas dos agentes de segurança e contém o nome, o número de telefone, a hora e o local do chamador, permitindo que a equipe de segurança responda rapidamente ao chamador de emergência usando uma mensagem instantânea ou voz.

5. Se você configurou uma política de local para conferência e ela suportar o provedor de serviços E9-1-1, um Suporte de Segurança interno estará na conferência em uma chamada com áudio unilateral ou bidirecional.

6. Se a chamada for interrompida prematuramente, o PSAP usa o número de retorno de chamada para entrar em contato com o chamador diretamente.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Roteamento de chamadas E9-1-1 usando um gateway ELIN

Alguns parceiros do Programa de interoperabilidade aberta de comunicações unificadas fornecem gateways ELIN (Emergency Location Identification Number) qualificados, que podem servir como uma alternativa para uma conexão de tronco SIP para um provedor de serviços E9-1-1 qualificado. Os gateways ELIN suportam conectividade ISDN ou CAMA (Centralized Automatic Message Accounting) para os serviços E9-1-1 baseados em PSTN (rede telefônica pública comutada). Para obter detalhes sobre parceiros que fornecem gateways ELIN e links para sua documentação, consulte Infraestrutura qualificada para [Microsoft Lync](https://go.microsoft.com/fwlink/p/?LinkId=248425) e Infraestrutura de [Telefonia para Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

Assim como as conexões de tronco SIP com provedores de serviços E9-1-1, os gateways ELIN também fornecem os meios de rotear uma chamada de emergência para o PSAP (Ponto de Atendimento Público Seguro) mais apropriado do chamador, mas esses gateways usam um ELIN como identificador de local. Defina ELINs para cada ERL (Local de Resposta de Emergência) em sua organização (para obter detalhes, consulte Gerenciar locais para [gateways ELIN](elin-gateways.md)no Skype for Business Server).

Ao usar um gateway ELIN para chamadas de emergência, você usa a mesma infraestrutura do Skype for Business Server E9-1-1 que usaria para uma conexão de tronco SIP. Ou seja, o banco de dados do serviço de Informações de Local fornece o local para o cliente Skype for Business, e a política de local habilita o recurso e define o roteamento. Com um gateway ELIN, no entanto, você precisa adicionar os ELINs ao banco de dados de serviço de Informações de Local e fazer com que sua operadora PSTN os carregue no banco de dados ali (Identificação automática de local).

Quando um cliente do Skype for Business obtém sua localização do serviço de Informações de Local, o local inclui o ELIN. Durante uma chamada de emergência, o ELIN é incluído com a localização enviada para o gateway ELIN. O gateway ELIN identifica a chamada como uma chamada de emergência e troca o número do chamador pela Elin. O gateway ELIN, em seguida, encaminha a chamada para o PSTN com o ELIN como o número de chamada. O provedor E9-1-1 do PSTN procura o ELIN no banco de dados ALI, que é um banco de dados que acompanha o banco de dados MSAG (Catálogo de Endereços Principal). O PSTN envia a chamada para o PSAP mais apropriado com base na pesquisa ALI, e o PSAP envia socorristas para a localização do chamador com base na pesquisa ALI. O número da chamada é armazenado em cache no gateway ELIN por uma quantidade de tempo pré-definida para retorno de chamadas. Durante uma chamada de retorno, o PSAP alcança o gateway ELIN, que troca o Elin pelo número da DID (discagem direta interna).

O gateway ELIN suporta chamadas de emergência somente de dentro da rede da sua organização. Eles não suportam chamadas de emergência feitas de fora da rede.

> [!NOTE]
> Para obter detalhes sobre o uso da conexão de tronco SIP para chamadas de emergência, consulte [Routing E9-1-1 Calls by Using a SIP Trunk](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx).

O diagrama a seguir mostra como uma chamada de emergência é roteada do Skype for Business Server para o PSAP quando você usa um gateway ELIN.

**Encaminhando chamadas de E9-1-1 com um gateway ELIN**

![Mostra como uma chamada para serviços de emergência passa pelo Servidor de Mediação e, em seguida, para o provedor de serviços de emergência. Depois disso, pode haver uma IM enviada para a segurança local e/ou uma chamada de retorno para o chamador original.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Um SIP INVITE que contém o local, o número de retorno de chamada do chamador e a URL de notificação (opcional) e o número de retorno de chamada em conferência são roteados para o Skype for Business Server.

2. O Skype for Business Server corresponde ao número de emergência e encaminha a chamada (com base no valor de Uso de **PSTN** definido na política de local aplicável) para um Servidor de Mediação e de lá para um gateway ELIN.

3. O gateway ELIN encaminha a chamada para o PSTN através de um tronco CAMA ou ISDN.

4. O PSTN identifica a chamada como uma chamada de emergência e a encaminha para um roteador E9-1-1 seletivo na rede. O roteador E9-1-1 seletivo pesquisa o número do chamador no banco de dados ALI para obter o local geográfico. O roteador E9-1-1 seletivo envia a chamada para o PSAP mais apropriado com base nas informações de local que foram recuperadas do banco de dados ALI.

5. Se você configurou a política de local para notificações, um ou mais funcionários de segurança da sua organização receberão uma mensagem instantânea especial de notificação de emergência do Skype for Business. Essa mensagem sempre aparece nas telas dos agentes de segurança e contém o nome, o número de telefone, a hora e o local do chamador, permitindo que a equipe de segurança responda rapidamente ao chamador de emergência usando uma mensagem instantânea ou voz.

6. Se a chamada for interrompida prematuramente, o PSAP usa o ELIN para entrar diretamente em contato com o chamador. O gateway ELIN troca o ELIN pela DID do chamador.


