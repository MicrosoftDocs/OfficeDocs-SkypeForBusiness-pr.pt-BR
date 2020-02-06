---
title: Planejar serviços de emergência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Saiba mais sobre os serviços Enhanced 9-1-1 (E9-1-1) no Skype for Business Server Enterprise Voice, incluindo aquisição de localização e roteamento de chamadas.
ms.openlocfilehash: f09729bc6fdbd2fa64dee5b30af88494cd618915
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802981"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Planejar serviços de emergência no Skype for Business Server

Saiba mais sobre os serviços Enhanced 9-1-1 (E9-1-1) no Skype for Business Server Enterprise Voice, incluindo aquisição de localização e roteamento de chamadas.

O Skype for Business Server é compatível com os serviços Enhanced 9-1-1 (E9-1-1) nos Estados Unidos, como parte de uma implantação do Enterprise Voice. O E9-1-1 é um recurso de expedição de emergência que associa uma chamada a 9-1-1 a uma ERL (Localização de Resposta à Emergência), que consiste em endereços cívicos (ou seja, ruas) e outras informações de local mais específicas, como os números dos andares, para ligações de prédios comerciais e outras instalações multilocatário. Com o uso da ERL fornecida, um PSAP (ponto de atendimento público seguro) pode expedir os serviços de emergência imediatamente ao chamador em apuros, com risco reduzido de direcionar o respondente de forma não intencional a um local incorreto ou ambíguo.

> [!NOTE]
> Agora o Skype for Business Server oferece suporte à configuração de vários números de emergência para um cliente. Para obter mais informações, consulte [planejar vários números de emergência no Skype for Business Server](multiple-emergency-numbers.md).

> [!NOTE]
> O Skype for Business Server tem três recursos avançados do Enterprise Voice: controle de admissão de chamadas, serviços de emergência (E9-1-1) e bypass de mídia. Para obter uma visão geral do planejamento de informações comuns a todos esses três recursos, consulte [configurações de rede para os recursos avançados de voz empresarial no Skype for Business Server](network-settings-for-advanced-features.md).

O Skype for Business Server é compatível com chamadas Enhanced 9-1-1 (E9-1-1) dos clientes do Skype for Business e dos dispositivos Lync Phone Edition. Quando você configura o Skype for Business Server para E9-1-1, as chamadas de emergência feitas pelo Skype for Business ou pelo Lync Phone Edition incluem informações de local de resposta de emergência (ERL) do banco de dados do serviço de informações de localização. ERLs consistem em endereços cívicos (rua) e outras informações que ajudam a identificar a localização mais precisa em prédios de escritórios e outras instalações com vários locatários. Quando um usuário faz uma chamada de emergência, o Skype for Business Server roteia o áudio da chamada, juntamente com o local e as informações de retorno de chamada, por meio de um servidor de mediação para um provedor de serviços E9-1-1. O provedor de serviços E9-1-1 usa o endereço cívico do chamador para encaminhar a chamada para PSAP (Ponto de Atendimento Público Seguro), que atende à localização do chamador e envia também uma ESQK (Chave de Consulta de Serviço de Emergência) que PSAP usa para procurar a ERL do chamador.

O Skype for Business Server oferece suporte a dois métodos de roteamento de chamadas de emergência para um provedor de serviços E9-1-1:

- Uma conexão de tronco SIP com um provedor de serviços E9-1-1 qualificado

- Um gateway ELIN (para um provedor de serviços E9-1-1 baseado em PSTN (Rede Telefônica Pública Comutada)

Quando você usa um provedor de serviço E9 de tronco SIP-1-1, adiciona ERLs ao banco de dados do serviço de informações de localização e, em seguida, valida os locais em relação a uma guia de endereço mestre (MSAG) mantida pelo provedor de serviços E9-1-1. Se um provedor de serviços E9-1-1 receber uma chamada que não tenha informações de localização ou tiver um local que não foi validado em relação ao MSAG, o provedor de serviços E9-1-1 roteia a chamada para um ECRC (central/regional Emergency Call Response Center), que é designado com um pessoal treinado especialmente que obtém verbalmente a localização do chamador, se possível, e encaminha manualmente a chamada para o PSAP apropriado. (Alguns provedores de serviços E9-1-1 de tronco SIP também fornecem aos clientes um número DID (discagem direta interna) de PSTN ao ECRC, que é um meio alternativo de encaminhar as chamadas 9-1-1 se um tronco SIP falhar por algum motivo).

Ao contrário dos telefones de PBX (PBX) de divisão de tempo (TDM) e de intercâmbio privado baseado em IP (PBX), que têm locais fixos, um ponto de extremidade do Skype for Business pode ser muito móvel. Quando você implanta o recurso E9-1-1, o Skype for Business Server ajuda a garantir que não importa onde um chamador está localizado, a chamada de emergência pode ser roteada para o PSAP que serve o local do autor do usuário. Por exemplo, se o escritório principal de um usuário estiver localizado em Redmond, Washington, mas o usuário fizer uma chamada de emergência de um computador em uma filial no Wichita, o Kansas, o tronco SIP ou o provedor de serviços E9-1 baseado em PSTN direcionará a chamada para o PSAP no Wichita , e não à PSAP em Redmond.

Ao usar um gateway ELIN, você também adiciona ERLs ao banco de dados do serviço de informações de localização, mas também inclui um número ELIN para cada local. O número ELIN se torna o número de discagem de emergência durante a chamada de emergência. Em seguida, é necessário verificar se a operadora PSTN carrega os ELINs no banco de dados de ALI (Identificação Automática de Local).

> [!NOTE]
> Skype para empresas-dispositivos analógicos conectados não podem receber informações de localização do serviço de informações de localização ou local de transmissão para o provedor de serviços E9-1-1.

 Se usar a opção do provedor de serviços E9-1-1 do tronco SIP e precisar dar suporte a E9-1-1 por meio de telefones analógicos, você terá duas opções:

- **Opção PS-ali tradicional** Se você tem gateways PSTN locais em cada site em que os telefones analógicos são implantados e cada telefone analógico tem um, você pode provisionar a localização do dispositivo analógico diretamente com um provedor de serviços de comutação particular/identificação automática de local (PS-ALI). Nesse caso, você deve configurar as políticas de voz do Skype for Business especialmente criadas e atribuí-las aos objetos de contato de dispositivo analógico para que as chamadas E9-1 desses telefones sejam roteadas diretamente pelo gateway local para o provedor de PSTN que presta serviços ao site (em vez disso de direcionar a chamada para um tronco SIP do provedor de serviços E9-1-1). Quando uma chamada de emergência é efetuada, um banco de dados em um provedor de PS-ALI associado ao tronco PSTN mapeia o DID de cada telefone analógico para um local físico e fornece esse local ao PSAP. Esses registros precisam ser atualizados com o provedor de serviços PS-ALI sempre que os telefones são movidos para ERLs diferentes.

- **Opção de provedor de serviços E9-1-1** Você pode registrar o DIDs de telefone analógico e seus ERLs correspondentes com o provedor de serviços E9-1-1, se for compatível com o provedor de serviços E9-1-1. Se o provedor receber uma chamada do Skype for Business Server que não inclua dados do PIDF-LO, o provedor poderá ver se há um banco de dados correspondente no número do participante da chamada. Ao usar o ERL recuperado do seu banco de dados, o provedor pode rotear automaticamente a chamada de emergência para o PSAP correto, e o PSAP receberá o DID do dispositivo analógico e um registro ESQK que permite ao dispatcher Pesquisar a localização do chamador.

Se você usar a opção de gateway ELIN e precisar oferecer suporte a E9-1-1 de telefones analógicos, é possível provisionar o local do dispositivo analógico diretamente com o provedor de serviços PS-ALI, como descrito na primeira opção acima.

De uma perspectiva do Skype for Business Server, o processo E9-1-1 pode ser separado em dois estágios:

- Estágio 1: aquisição de local

- Estágio 2: encaminhamento de chamada de emergência para um provedor de serviços E9-1-1

Esta seção descreve como esses estágios funcionam.

Se planeja configurar sua infraestrutura para detectar automaticamente o local do cliente, primeiro você precisa decidir quais elementos de rede serão usados para mapear os chamadores para os locais. Para obter detalhes sobre as possíveis opções, consulte [definir os elementos de rede usados para determinar o local no Skype for Business Server](network-location.md).

## <a name="acquiring-a-location"></a>Adquirindo um local

Em uma implantação do Skype for Business Server E9-1-1, todos os clientes do Skype for Business ou Lync Phone Edition conectados internamente adquirem ativamente seu próprio local. Após o registro do SIP, o cliente fornece todas as informações de conectividade de rede que ele conhece em si em uma solicitação de localização para o serviço de informações de localização, que é um serviço da Web apoiado por um banco de dados replicado do SQL Server. Cada pool de sites central tem um serviço de informações de localização, que usa as informações de rede para consultar seus registros para um local correspondente. Se houver uma correspondência, o serviço de informações de localização retornará um local ao cliente. Caso contrário, o usuário poderá ser solicitado a inserir o local manualmente (dependendo das configurações de política de local). Os dados do local são transmitidos de volta ao cliente em um formato XML padronizado IETF (Internet Engineering Task Force) chamado PIDF-LO (Presence Information Data Format Location Object).

O cliente Skype for Business inclui os dados de PIDF como parte de uma chamada de emergência, e esses dados são usados pelo provedor de serviços E9-1-1 para determinar o PSAP apropriado e direcionar a chamada para esse PSAP juntamente com o ESQK correto, o que permite que o Dispatcher do PSAP obter a localização do chamador.

O diagrama a seguir mostra como um cliente Skype for Business adquire um local (exceto para o método de local baseado em endereço MAC do cliente de terceiros):

![Como o cliente adquire um diagrama de localização](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Para um cliente adquirir um local, as seguintes etapas devem ser executadas:

1. O administrador preenche o banco de dados do serviço de informações de localização com o wiremap de rede (tabelas que mapeiam vários tipos de endereços de rede para locais de reação de emergência correspondentes (ERLs)).

2. Se você usar um provedor de serviços E9-1-1 do tronco SIP, o administrador validará as partes de endereço cívico do ERLs em comparação com um banco de dados MSAG (Catálogo de Endereços Principal) mantido pelo provedor do serviços E9-1-1. Se você usar um gateway ELIN, o administrador garante que a operadora de PSTN fará o upload dos ELINs para o banco de dados de Identificação de local automática (ALI).

3. Durante o registro ou sempre que ocorre uma alteração na rede, um cliente conectado internamente envia uma solicitação de localização que contém os endereços de rede descobertos do cliente para o serviço de informações de localização.

4. O serviço de informações de localização consulta os registros publicados de um local e, se for encontrada uma coincidência, retorna o ERL para o cliente no formato PIDF-LO.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Encaminhamento de chamadas E9-1-1 usando um tronco SIP

Usar um tronco SIP para conectar-se a um provedor de serviços de E9-1-1 qualificado é um modo pelo qual você pode implantar E9-1-1. Para obter detalhes sobre usar um gateway ELIN para se conectar a um provedor de serviços de E9-1-1 baseado em PSTN (rede telefônica pública comutada), veja [Routing E9-1-1 Calls by Using an ELIN Gateway](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).

O diagrama a seguir mostra como uma chamada de emergência é roteada do Skype for Business Server para o ponto de resposta de segurança pública (PSAP) quando você usa um tronco SIP e um provedor de serviços E9-1 qualificado.

**Encaminhamento de chamadas E9-1-1 através de um tronco SIP**

![Roteamento de chamadas de emergência do Lync Server para PSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Quando uma chamada de emergência é feita de um cliente compatível do Skype for Business Server:

1. Um convite SIP que contém o local, o número de retorno de chamada do chamador e a URL de notificação (opcional) e o número de retorno de chamada de conferência é roteado para o Skype for Business Server.

2. O Skype for Business Server corresponde ao número de emergência e roteia a chamada (com base no valor de **uso de PSTN** definido na política de localização aplicável) para um servidor de mediação e, a partir daí, em um tronco SIP para o provedor de serviços E9-1-1.

3. O provedor de serviços E9-1-1 encaminha a chamada de emergência ao PSAP correto baseado no local que é fornecido com a chamada. Quando o cliente inclui um ERL (local de resposta de emergência) com a chamada de emergência, o provedor automaticamente encaminha a chamada ao PSAP adequado. Caso o local tenha sido manualmente inserido pelo usuário, o ECRC (centro de resposta de chamadas de emergência) primeiro verifica verbalmente a precisão do local com o chamador antes de encaminhar a chamada de emergência ao PSAP.

4. Se você configurou a política de localização para notificações, um ou mais gerentes de segurança da sua organização receberão uma mensagem de chat especial de notificação de emergência do Skype for Business. Essa mensagem sempre aparece na (s) tela (s) dos responsáveis pela segurança e contém o nome, o número de telefone, a hora e a localização do chamador, permitindo que a equipe de segurança responda rapidamente ao chamador de emergência usando uma mensagem de chat ou voz.

5. Caso tenha configurado a política de local para conferências e ela seja suportada pelo provedor de serviços E9-1-1, um Suporte de Segurança é colocado na chamada com áudio uni ou bidirecional.

6. Caso a chamada seja interrompida prematuramente, o PSAP usa o número de retorno de chamada para entrar em contato diretamente com o chamador.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Roteamento de chamadas E9-1-1 usando um gateway ELIN

Alguns parceiros do Programa de Interoperabilidade Aberta de Comunicações Unificadas fornecem gateways compatíveis com ELIN (número de identificação de local de emergência) qualificados, que podem servir como uma alternativa a uma conexão de tronco SIP com um provedor de serviços E9-1-1 qualificado. Os gateways ELIN dão suporte à conectividade CAMA (Contabilidade de Mensagem Automática Centralizada) ou ISDN com serviços E9-1-1 baseados em PSTN (Rede Telefônica Pública Comutada). Para obter detalhes sobre os parceiros que fornecem gateways do ELIN e links para a documentação dele, consulte [infraestrutura qualificada para Microsoft Lync](https://go.microsoft.com/fwlink/p/?LinkId=248425) e [infraestrutura de telefonia para o Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

Assim como as conexões de tronco SIP com provedores de serviços E9-1-1, os gateways ELIN também fornecem um meio de encaminhar uma chamada de emergência para o PSAP (Ponto de Atendimento Público Seguro) mais apropriado do chamador, mas esses gateways usam um ELIN como identificador do local. Você define ELINs para cada local de resposta de emergência (ERL) em sua organização (para obter detalhes, consulte [gerenciar locais para gateways Elin no Skype for Business Server](elin-gateways.md)).

Ao usar um gateway ELIN para chamadas de emergência, você usa a mesma infraestrutura do Skype for Business Server E9-1 que você usaria para uma conexão de tronco SIP. Ou seja, o banco de dados do serviço de informações de localização fornece o local para o cliente do Skype for Business, e a política de localização habilita o recurso e define o roteamento. No entanto, com um gateway ELIN, você precisa adicionar o ELINs ao banco de dados do serviço de informações de localização e ter sua operadora PSTN carregá-los para o banco de dados de identificação automática de local (ALI).

Quando um cliente Skype for Business obtém seu local do serviço de informações de localização, o local inclui o ELIN. Durante uma chamada de emergência, o ELIN é incluído no local enviado para o gateway ELIN. O gateway ELIN identifica a chamada como uma chamada de emergência e troca o número do chamador pelo ELIN. Em seguida, o gateway de ELIN encaminha a chamada para a PSTN com o ELIN como número chamador. O provedor de E9-1-1 da PSTN pesquisa o ELIN no banco de dados ALI, que é um banco de dados complementar ao banco de dados MSAG (Catálogo de Endereços Principal). A PSTN então envia a chamada para o PSAP mais apropriado com base na pesquisa do ALI, e o PSAP envia as equipes de emergência para o local do chamador com base na pesquisa do ALI. O número chamador é armazenado em cache no gateway ELIN por um tempo predefinido para retornos de chamada. Durante um retorno de chamada, o PSAP chega ao gateway ELIN, que troca o ELIN pelo número DID (discagem direta interna) do chamador.

Os gateways ELIN oferecem suporte a chamadas de emergência somente de dentro da rede da sua organização. Eles não oferecem suporte a chamadas de emergência realizadas fora da sua rede.

> [!NOTE]
> Para obter detalhes sobre como usar uma conexão de tronco SIP para chamadas de emergência, veja [Routing E9-1-1 Calls by Using a SIP Trunk](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx).

O diagrama a seguir mostra como uma chamada de emergência é roteada do Skype for Business Server para o PSAP quando você usa um gateway ELIN.

**Encaminhar chamadas de E9-1-1 com um gateway ELIN**

![Mostra como uma chamada para serviços de emergência viaja pelo servidor de mediação e, em seguida, para o provedor de serviços de emergência. Depois disso, pode ser uma mensagem de chat enviada para a segurança no local e/ou uma chamada de volta para o chamador original.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Um convite SIP contendo o local, o número de retorno de chamada do chamador e a URL de notificação (opcional) e o número de retorno de chamada de conferência são roteados para o Skype for Business Server.

2. O Skype for Business Server corresponde ao número de emergência e, em seguida, roteia a chamada (com base no valor de **uso de PSTN** definido na política de localização aplicável) para um servidor de mediação e de lá para um gateway Elin.

3. O gateway ELIN encaminha a chamada para o PSTN por meio de um tronco CAMA ou ISDN.

4. O PSTN identifica a chamada como uma chamada de emergência e a encaminha para um roteador E9-1-1 seletivo na rede. O roteador E9-1-1 seletivo pesquisa o número do chamador no banco de dados ALI para obter o local geográfico. O roteador E9-1-1 seletivo envia a chamada para o PSAP mais apropriado com base nas informações de local que foram recuperadas do banco de dados ALI. 

5. Se você configurou a política de localização para notificações, um ou mais gerentes de segurança da sua organização receberão uma mensagem de chat especial de notificação de emergência do Skype for Business. Essa mensagem sempre aparece na (s) tela (s) dos responsáveis pela segurança e contém o nome, o número de telefone, a hora e a localização do chamador, permitindo que a equipe de segurança responda rapidamente ao chamador de emergência usando uma mensagem de chat ou voz.

6. Se a chamada for interrompida prematuramente, o PSAP usará o ELIN para contatar diretamente o chamador. O gateway ELIN trocará o ELIN pelo DID do chamador.


