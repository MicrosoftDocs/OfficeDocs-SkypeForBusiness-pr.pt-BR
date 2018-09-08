---
title: Planejamento de serviços de emergência no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: Saiba mais sobre os serviços do Enhanced 9-1-1 (E9-1-1) no Skype para Business Server Enterprise Voice, incluindo a aquisição de local e o roteamento de chamada.
ms.openlocfilehash: 19c660152903c1091612060bfd808bea5a116d2f
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884389"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Planejamento de serviços de emergência no Skype para Business Server

Saiba mais sobre os serviços do Enhanced 9-1-1 (E9-1-1) no Skype para Business Server Enterprise Voice, incluindo a aquisição de local e o roteamento de chamada.

Skype para Business Server oferece suporte a serviços do Enhanced 9-1-1 (E9-1-1) nos Estados Unidos como parte de uma implantação do Enterprise Voice. O E9-1-1 é um recurso de expedição de emergência que associa uma chamada a 9-1-1 a uma ERL (Localização de Resposta à Emergência), que consiste em endereços cívicos (ou seja, ruas) e outras informações de local mais específicas, como os números dos andares, para ligações de prédios comerciais e outras instalações multilocatário. Com o uso da ERL fornecida, um PSAP (ponto de atendimento público seguro) pode expedir os serviços de emergência imediatamente ao chamador em apuros, com risco reduzido de direcionar o respondente de forma não intencional a um local incorreto ou ambíguo.

> [!NOTE]
> Skype para Business Server agora oferece suporte a configuração de vários números de emergências para um cliente. Para obter mais informações, consulte [Planejar vários números de emergências Skype para Business Server](multiple-emergency-numbers.md).

> [!NOTE]
> Skype para Business Server tem três recursos avançados do Enterprise Voice: bypass de mídia, serviços de emergência (E9-1-1) e controle de admissão de chamada. Para obter uma visão geral do planejamento de informações que são comuns a todos os três desses recursos, consulte [configurações de rede para os recursos avançados do Enterprise Voice no Skype para Business Server](network-settings-for-advanced-features.md).

Skype para Business Server suporta Enhanced 9-1-1 (E9-1-1) chamando do Skype para clientes corporativos e dispositivos Lync Phone Edition. Quando você configurar Skype do Business Server para chamadas de E9-1-1, emergências feitas do Skype para negócios ou o Lync Phone Edition incluem informações de local de resposta de emergência (ERL) do banco de dados de serviço de informações de local. ERLs consistem em endereços cívicos (rua) e outras informações que ajudam a identificar a localização mais precisa em prédios de escritórios e outras instalações com vários locatários. Quando um usuário faz uma chamada de emergência, Skype para Business Server encaminha o áudio da chamada, junto com as informações de local e o retorno de chamada, por meio de um servidor de mediação para um provedor de serviço E9-1-1. O provedor de serviços E9-1-1 usa o endereço cívico do chamador para encaminhar a chamada para PSAP (Ponto de Atendimento Público Seguro), que atende à localização do chamador e envia também uma ESQK (Chave de Consulta de Serviço de Emergência) que PSAP usa para procurar a ERL do chamador.

Skype para Business Server suporta dois métodos de roteamento de chamadas de emergência para um provedor de serviço E9-1-1:

- Uma conexão de tronco SIP com um provedor de serviços E9-1-1 qualificado

- Um gateway ELIN (para um provedor de serviços E9-1-1 baseado em PSTN (Rede Telefônica Pública Comutada)

Quando você usa um provedor de serviços de E9-1-1 de tronco SIP, você adiciona ERLs no banco de dados de serviço de informações de local e, em seguida, valida os locais contra um endereço guia Rua (MSAG) mantido pelo provedor de serviços E9-1-1. Se um provedor de serviço E9-1-1 recebe uma chamada que não possui informações de local ou que tenha um local que não foi validado mediante ao MSAG, o provedor de serviços E9-1-1 encaminha a chamada para uma emergência chamada resposta Center (ECRC), que é nacionais/regionais com as equipes especialmente treinados pessoal verbalmente obter a localização do chamador com, se possível e manualmente rotear a chamada para o PSAP apropriado. (Alguns provedores de serviços E9-1-1 de tronco SIP também fornecem aos clientes um número DID (discagem direta interna) de PSTN ao ECRC, que é um meio alternativo de encaminhar as chamadas 9-1-1 se um tronco SIP falhar por algum motivo).

Ao contrário com base em IP privada de comutação telefônica (PBX) telefones e multiplexação de divisão de tempo (TDM), que têm locais fixos, um Skype para o ponto de extremidade de negócios pode ser muito móvel. Quando você implanta o recurso de E9-1-1, Skype para Business Server ajuda a garantir a que não importa onde um chamador está localizado, a chamada de emergência possa ser roteada para o PSAP que serve a localização do chamador. Por exemplo, se o escritório principal de um usuário está localizado em Redmond, Washington, mas o usuário faz uma chamada de emergência de um computador em uma filial em Wichita, Kansas, o tronco SIP ou o provedor de serviço baseado em PSTN E9-1-1 roteará a chamada para o PSAP em Wichita , não para o PSAP em Redmond.

Quando você usa um gateway ELIN, você também adicionar ERLs no banco de dados de serviço de informações de local, mas você também incluir um número ELIN para cada localidade. O número ELIN se torna o número de discagem de emergência durante a chamada de emergência. Em seguida, é necessário verificar se a operadora PSTN carrega os ELINs no banco de dados de ALI (Identificação Automática de Local).

> [!NOTE]
> Skype para dispositivos analógicos conectados corporativos não pode receber informações de local do serviço de informações de local ou transmitir local para o provedor de serviços E9-1-1.

 Se usar a opção do provedor de serviços E9-1-1 do tronco SIP e precisar dar suporte a E9-1-1 por meio de telefones analógicos, você terá duas opções:

- **PS-ALI tradicional de opção** Se você tiver os gateways PSTN locais em cada site onde telefones analógicos são implantados e cada telefone analógica tem um DID, você pode provisionar o local do dispositivo analógico diretamente com um provedor de serviços de identificação de local privada Switch/automática (ALI PS). Nesse caso, você configurar Skype especialmente criado para políticas de voz de negócios e atribuí-las ao dispositivo analógico objetos de contato para que as chamadas de E9-1-1 desses telefones encaminhe diretamente através do gateway local para o provedor PSTN que o site de serviços (em vez disso de rotear a chamada para um provedor de serviço E9-1-1 SIP tronco). Quando uma chamada de emergência é efetuada, um banco de dados em um provedor de PS-ALI associado ao tronco PSTN mapeia o DID de cada telefone analógico para um local físico e fornece esse local ao PSAP. Esses registros precisam ser atualizados com o provedor de serviços PS-ALI sempre que os telefones são movidos para ERLs diferentes.

- **Opção de provedor de serviço de E9-1-1** Você pode registrar os DIDs de telefone analógica e seus ERLs correspondentes com o provedor de serviço E9-1-1, se isso for suportado pelo provedor de serviços E9-1-1. Se o provedor recebe uma chamada do Skype para servidor de negócios que não inclui os dados de PIDF-LO, o provedor pode ver se houver uma correspondência de banco de dados no número DID do chamador. Usando o ERL recuperado do seu banco de dados, o provedor de pode automaticamente a rota de chamada de emergência para o PSAP correto e o PSAP receberá a DID do dispositivo analógico e um registro ESQK que permite que o distribuidor procurar a localização do chamador.

Se você usar a opção de gateway ELIN e precisar oferecer suporte a E9-1-1 de telefones analógicos, é possível provisionar o local do dispositivo analógico diretamente com o provedor de serviços PS-ALI, como descrito na primeira opção acima.

A partir de um Skype para perspectiva Business Server, o processo E9-1-1 pode ser separado em dois estágios:

- Estágio 1: aquisição de local

- Estágio 2: encaminhamento de chamada de emergência para um provedor de serviços E9-1-1

Esta seção descreve como esses estágios funcionam.

Se planeja configurar sua infraestrutura para detectar automaticamente o local do cliente, primeiro você precisa decidir quais elementos de rede serão usados para mapear os chamadores para os locais. Para obter detalhes sobre as opções possíveis, consulte [Define os elementos de rede usados para determinar o local em Skype para Business Server](network-location.md).

## <a name="acquiring-a-location"></a>Adquirindo um local

Em um Skype para implantação de servidor de negócios E9-1-1, a cada Skype conectado internamente para Lync Phone Edition ou negócios do cliente adquire ativamente seu próprio local. Após o registro SIP, o cliente fornece todas as informações de conectividade de rede que ele conheça próprio-la em uma solicitação de localização para o serviço de informações de local, que é um serviço web feito por um banco de dados replicado do SQL Server. Cada pool do site central tem um serviço de informações de local, que usa as informações de rede para consultar seus registros para um local correspondente. Se houver uma correspondência, o serviço de informações de localização retorna um local para o cliente. Caso contrário, o usuário poderá ser solicitado a inserir o local manualmente (dependendo das configurações de política de local). Os dados do local são transmitidos de volta ao cliente em um formato XML padronizado IETF (Internet Engineering Task Force) chamado PIDF-LO (Presence Information Data Format Location Object).

O Skype para o cliente de negócios inclui os dados de PIDF-LO como parte de uma chamada de emergência e esses dados são usados pelo provedor de serviços E9-1-1 para determinar o PSAP apropriado e rotear a chamada para esse PSAP juntamente com o ESQK correto, que permite que o distribuidor PSAP para obter a localização do chamador.

O diagrama a seguir mostra como um Skype para o cliente de negócios adquire um local (exceto para o método de localização com base no endereço MAC do cliente terceirizado):

![Diagrama de Como o cliente adquire um local](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Para um cliente adquirir um local, as seguintes etapas devem ser executadas:

1. O administrador preenche o banco de dados de serviço de informações de local com um wiremap de rede (tabelas que mapeiam vários tipos de endereços de rede para (corresponderem aos ERLs) correspondente Emergency Response Locations).

2. Se você usar um provedor de serviços E9-1-1 do tronco SIP, o administrador validará as partes de endereço cívico do ERLs em comparação com um banco de dados MSAG (Catálogo de Endereços Principal) mantido pelo provedor do serviços E9-1-1. Se você usar um gateway ELIN, o administrador garante que a operadora de PSTN fará o upload dos ELINs para o banco de dados de Identificação de local automática (ALI).

3. Durante o registro ou sempre que uma alteração na rede ocorre, um cliente conectado internamente enviará uma solicitação de localização que contém o cliente descoberto do endereços de rede para o serviço de informações de local.

4. O serviço de informações de local consulta seus registros publicados para um local e, se uma correspondência for encontrada, retornará o ERL ao cliente em formato PIDF-LO.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Encaminhamento de chamadas E9-1-1 usando um tronco SIP

Usar um tronco SIP para conectar-se a um provedor de serviços de E9-1-1 qualificado é um modo pelo qual você pode implantar E9-1-1. Para obter detalhes sobre como usar um gateway ELIN para se conectar a uma rede telefônica pública comutada (PSTN)-based E9-1-1 provedor de serviços, consulte [Roteamento de chamadas de E9-1-1 usando um Gateway ELIN](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).

O diagrama a seguir mostra como uma chamada de emergência é encaminhada do Skype para Business Server para o PSAP atendimento público seguro ponto () quando você usa um tronco SIP e o provedor de serviço qualificado E9-1-1.

**Encaminhamento de chamadas E9-1-1 através de um tronco SIP**

![Roteamento da chamada de emergência do Lync Server para PSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Quando uma chamada de emergência é feita de uma Skype compatível para o cliente Business Server:

1. Um SIP INVITE que contém o local, o número de retorno de URL de notificação e de conferência (opcional) e número de retorno de chamada do chamador é encaminhado para Skype para Business Server.

2. Skype para Business Server corresponde ao número de emergência e direciona a chamada (com base no valor **Uso** do PSTN definido na política de local aplicável) para um servidor de mediação e a partir daí, um tronco SIP para o provedor de serviço E9-1-1.

3. O provedor de serviços E9-1-1 encaminha a chamada de emergência ao PSAP correto baseado no local que é fornecido com a chamada. Quando o cliente inclui um ERL (local de resposta de emergência) com a chamada de emergência, o provedor automaticamente encaminha a chamada ao PSAP adequado. Caso o local tenha sido manualmente inserido pelo usuário, o ECRC (centro de resposta de chamadas de emergência) primeiro verifica verbalmente a precisão do local com o chamador antes de encaminhar a chamada de emergência ao PSAP.

4. Se você configurou a diretiva de local para notificações, um ou mais dos diretores de segurança da sua organização são enviadas de um Skype especial de mensagem instantânea de notificação de emergência de negócios. Esta mensagem sempre aparece na screen(s) dos diretores de segurança e contém o nome do chamador, número de telefone, hora e local, permitindo que o pessoal de segurança para responder rapidamente para o chamador de emergência usando uma mensagem instantânea ou voz.

5. Caso tenha configurado a política de local para conferências e ela seja suportada pelo provedor de serviços E9-1-1, um Suporte de Segurança é colocado na chamada com áudio uni ou bidirecional.

6. Caso a chamada seja interrompida prematuramente, o PSAP usa o número de retorno de chamada para entrar em contato diretamente com o chamador.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Roteamento de chamadas E9-1-1 usando um gateway ELIN

Alguns parceiros do Programa de Interoperabilidade Aberta de Comunicações Unificadas fornecem gateways compatíveis com ELIN (número de identificação de local de emergência) qualificados, que podem servir como uma alternativa a uma conexão de tronco SIP com um provedor de serviços E9-1-1 qualificado. Os gateways ELIN dão suporte à conectividade CAMA (Contabilidade de Mensagem Automática Centralizada) ou ISDN com serviços E9-1-1 baseados em PSTN (Rede Telefônica Pública Comutada). Para obter detalhes sobre parceiros que oferecem gateways ELIN e links para as documentações, consulte [infraestrutura qualificada do Microsoft Lync](https://go.microsoft.com/fwlink/p/?LinkId=248425) e [Infraestrutura de telefonia para Skype para negócios](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

Assim como as conexões de tronco SIP com provedores de serviços E9-1-1, os gateways ELIN também fornecem um meio de encaminhar uma chamada de emergência para o PSAP (Ponto de Atendimento Público Seguro) mais apropriado do chamador, mas esses gateways usam um ELIN como identificador do local. Definir ELINs para cada local de resposta de emergência (ERL) em sua organização (para obter detalhes, consulte [Gerenciar locais para gateways ELIN no Skype para Business Server](elin-gateways.md)).

Quando você usa um gateway ELIN para chamadas de emergência, use o mesmo Skype de infra-estrutura de servidor de negócios E9-1-1 que você deseja usar para uma conexão de tronco SIP. Ou seja, o banco de dados de serviço de informações de local fornece o local para o Skype para o cliente de negócios e a diretiva de local habilita o recurso e define o roteamento. Com um gateway ELIN, no entanto, você precisa adicionar os ELINs no banco de dados de serviço de informações de local e ter sua operadora da PSTN carregá-las no banco de dados de identificação de local automática (ALI).

Quando um Skype para o cliente de negócios obtém seu local do serviço de informações de local, a localidade inclui o ELIN. Durante uma chamada de emergência, o ELIN é incluído no local enviado para o gateway ELIN. O gateway ELIN identifica a chamada como uma chamada de emergência e troca o número do chamador pelo ELIN. Em seguida, o gateway de ELIN encaminha a chamada para a PSTN com o ELIN como número chamador. O provedor de E9-1-1 da PSTN pesquisa o ELIN no banco de dados ALI, que é um banco de dados complementar ao banco de dados MSAG (Catálogo de Endereços Principal). A PSTN então envia a chamada para o PSAP mais apropriado com base na pesquisa do ALI, e o PSAP envia as equipes de emergência para o local do chamador com base na pesquisa do ALI. O número chamador é armazenado em cache no gateway ELIN por um tempo predefinido para retornos de chamada. Durante um retorno de chamada, o PSAP chega ao gateway ELIN, que troca o ELIN pelo número DID (discagem direta interna) do chamador.

Os gateways ELIN oferecem suporte a chamadas de emergência somente de dentro da rede da sua organização. Eles não oferecem suporte a chamadas de emergência realizadas fora da sua rede.

> [!NOTE]
> Para obter detalhes sobre como usar uma conexão de tronco SIP para chamadas de emergência, consulte [Roteamento de chamadas de E9-1-1 usando um tronco SIP](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx).

O diagrama a seguir mostra como uma chamada de emergência é encaminhada do Skype para Business Server para o PSAP quando você usa um gateway ELIN.

**Encaminhar chamadas de E9-1-1 com um gateway ELIN**

![Mostra como uma chamada para serviços de emergência percorre o Servidor de Mediação e depois prossegue até o provedor de serviços de emergência. Depois disso, há a opção de enviar uma mensagem instantânea à segurança do local e/ou uma chamada de volta ao chamador original.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Um SIP INVITE contendo o local, o número de retorno de URL de notificação e de conferência (opcional) e número de retorno de chamada do chamador é encaminhado para Skype para Business Server.

2. Skype para Business Server corresponde ao número de emergência e encaminha a chamada (com base no valor do **Uso do PSTN** definido na política de local aplicável) para um servidor de mediação e de lá para um gateway ELIN.

3. O gateway ELIN encaminha a chamada para o PSTN por meio de um tronco CAMA ou ISDN.

4. O PSTN identifica a chamada como uma chamada de emergência e a encaminha para um roteador E9-1-1 seletivo na rede. O roteador E9-1-1 seletivo pesquisa o número do chamador no banco de dados ALI para obter o local geográfico. O roteador E9-1-1 seletivo envia a chamada para o PSAP mais apropriado com base nas informações de local que foram recuperadas do banco de dados ALI. 

5. Se você configurou a diretiva de local para notificações, um ou mais dos diretores de segurança da sua organização são enviadas de um Skype especial de mensagem instantânea de notificação de emergência de negócios. Esta mensagem sempre aparece na screen(s) dos diretores de segurança e contém o nome do chamador, número de telefone, hora e local, permitindo que o pessoal de segurança para responder rapidamente para o chamador de emergência usando uma mensagem instantânea ou voz.

6. Se a chamada for interrompida prematuramente, o PSAP usará o ELIN para contatar diretamente o chamador. O gateway ELIN trocará o ELIN pelo DID do chamador.


