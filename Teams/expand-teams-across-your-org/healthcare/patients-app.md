---
title: Visão geral de aplicativo de pacientes
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Integração de EHR app pacientes de equipes da Microsoft
ms.openlocfilehash: 25eb1b4ee09eec8395db2ac821d19624a508c937
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643069"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Integrando registros de saúde eletrônicos em equipes da Microsoft

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Este artigo destina-se um desenvolvedor de IT interessado em usar APIs FHIR na parte superior de um sistema de informações médicas para se conectar ao Microsoft Teams de saúde geral. Isso permitiria cenários de coordenação de atendimento médico que correspondem às necessidades de uma organização de saúde.

Este artigo documenta as especificações de interface FHIR para o aplicativo Microsoft equipes pacientes e compreensão que é necessária para configurar um servidor FHIR e conectando-se para o aplicativo de pacientes em sua environment\tenant de desenvolvimento. Você também precisará estar familiarizado com a documentação do servidor FHIR que tiver escolhido, que deve ser uma das opções com suporte:
- Datica (por meio da oferta seus [CMI](https://datica.com/compliant-managed-integration/) )
- Informações Cloverleaf (pela [Ponte de FHIR informações](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (por meio do [R ^ server FHIR](https://www.redoxengine.com/fhir/))
- Dapasoft (por meio de [Corolar em FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

> [!NOTE]
> Esse processo não inclui etapas que usam o Centro de administração do Microsoft Teams ou cmdlets do PowerShell para habilitar recursos. A configuração é feita inteiramente no lado do serviço do servidor FHIR e no cliente app os pacientes.

Ilustrada abaixo é a arquitetura do aplicativo os pacientes:

![Arquitetura do aplicativo de pacientes](../../media/patients-app-architecture.png)

As seções a seguir explicam os requisitos da camada de acesso de dados somente FHIR para o aplicativo de pacientes que um servidor FHIR (ou EHR habilitado FHIR APIs) deve atender para integrar com o aplicativo de pacientes, incluindo o seguinte:

- Expectativas em torno de autenticação do usuário
- Requisitos técnicos e funcionais da interface de integração
- Expectativas em torno de desempenho e confiabilidade
- Expectativas em torno de recursos FHIR ser suportados para o aplicativo de pacientes
- Processo de integração e o modelo de contrato esperada
- Como registrar a mesmo e seu cliente na visualização particular do aplicativo os pacientes
- Como começar com FHIR e alguns comuns desafios enfrentados com o aplicativo de pacientes
- Requisitos futuros na iteração seguinte do aplicativo os pacientes

> [!NOTE]
> A palavra "parceiro" ou "interoperabilidade" é usado para se referir a qualquer participante 3º organização que habilita a integração com sistemas EHR para o aplicativo de pacientes através de FHIR e está implementando um servidor FHIR para coincidir com as especificações listadas nas seções a seguir.

## <a name="functional-and-technical-requirements"></a>Requisitos técnicos e funcionais  

### <a name="authentication"></a>Autenticação  

Autorização de nível de aplicativo *com não há suporte para autorização de nível de usuário* é a maneira mais comumente suportada execute transformações de dados e que exponha conexões EHR dados por meio de FHIR, mesmo que o sistema EHR pode implementar a autorização de nível de usuário . O serviço de interoperabilidade (parceiro) obtém elevado acesso aos dados EHR, e quando eles expor os mesmos dados como os recursos apropriados de FHIR há nenhum contexto de autorização passado para o consumidor de serviço de interoperabilidade (o aplicativo de pacientes) integração com a interoperabilidade Serviço ou outra plataforma. O aplicativo de pacientes não poderão aplicar a autorização de nível de usuário, mas oferece suporte à autenticação de aplicativo entre o aplicativo de pacientes e serviço de interoperabilidade do parceiro.

O modelo de autenticação do aplicativo é descrito a seguir:

Serviço de autenticação do serviço deve ser feito pelo OAuth 2.0 [fluxo de credencial do cliente](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/). O serviço de parceiro precisa fornecer o seguinte:

1. O serviço de parceiro habilita o aplicativo de pacientes criar uma conta com o parceiro, que permite que o aplicativo de pacientes gerar e próprio client_id e client_secret, gerenciado por meio de um portal de registro de autenticação no servidor de autenticação do parceiro.
2. O serviço de parceiro possui o sistema de autenticação/autorização, que aceita e verifica (autentica) o cliente credenciais fornecida e fornece um token de acesso com a dica de Inquilino no escopo, conforme descrito abaixo.
3. Por motivos de segurança ou no caso de uma violação secreta, o aplicativo de pacientes pode gerar novamente o segredo e invalidar ou excluir o segredo antigo (o exemplo do mesmo é disponível no Portal do Windows Azure - AAD App registro)
4. O ponto de extremidade de metadados a declaração de conformidade de hospedagem deve ser não autenticado, ele deve ser acessado sem token de autenticação.
5. O serviço de parceiro fornece o ponto de extremidade de token para o aplicativo de pacientes solicitar um token de acesso usando um fluxo de credencial do cliente. A url de token de acordo com o servidor de autorização deve ser parte da declaração de conformidade (recurso) FHIR obtida de metadados no servidor FHIR como neste exemplo:

![Os pacientes app 5](../../media/Patient-app-5.png)

Uma solicitação para um token de acesso consiste dos seguintes parâmetros:

    POST /token HTTP/1.1
    Host: authorization-server.com

    grant-type=client_credentials
    &client_id=xxxxxxxxxx
    &client_secret=xxxxxxxxxx

O serviço de parceiro fornece o client_id e client_secret para os pacientes app, gerenciado por meio de um portal de registro de autenticação no lado do parceiro. O serviço de parceiro fornece o ponto de extremidade para o token de acesso de solicitação usando um fluxo de credencial do cliente. Uma resposta bem-sucedida deve incluir os parâmetros token_type, access_token e expires_in.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Roteamento: O mapeamento AAD locatário para o ponto de extremidade de provedor

O aplicativo de pacientes se conecta a um serviço de parceiro por meio de um único ponto de extremidade. O serviço de parceiro proprietária e mantém um mecanismo para mapear cada cliente da Microsoft (ID do inquilino AAD) a um provedor de saúde respectivo (server FHIR) que trabalha com o serviço de parceiro.

Mapeando inquilino AAD para um ponto de extremidade do provedor usa o ID de Inquilino AAD (GUID). O aplicativo de pacientes passa a ID do inquilino no escopo, ao mesmo tempo em que está solicitando um token de acesso para cada solicitação. O serviço de parceiro mantém o mapeamento de ID do inquilino ao ponto de extremidade de provedor e redireciona as solicitações para um ponto de extremidade do provedor com base na identificação do inquilino. Para fazer isso, o parceiro oferece suporte à configuração do seu lado (manualmente ou através de um portal como parte de inclusão de organizações de provedor para sua plataforma de interoperabilidade).

O fluxo de trabalho de autenticação e de roteamento é mostrado abaixo:

![Os pacientes app 6](../../media/Patient-app-6.png)

1. Solicitação de token de acesso de app enviando:
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. Responder com um token de app:

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. Solicite dados protegidos com o token de acesso.
4. Mensagem de autorização: selecione o servidor FHIR apropriado para rotear para da ID do inquilino no escopo
5. Envia os dados de aplicativo protegido do servidor FHIR autorizado depois de autenticar com o token de app.

## <a name="interfaces"></a>Interfaces

Chamadas específicas e campos usados pelo app os pacientes são documentados nos artigos a seguir. Selecione a interface aplicável ao seu servidor FHIR/FHIR APIs.

- [Especificação de interface de DSTU2](dstu2-interface.md)
- [Especificação de interface de STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Desempenho e confiabilidade

Enquanto o aplicativo de pacientes está no modo de visualização particular, há não garantimos o desempenho de ponta a ponta. Fatores de desempenho incluem as latências relativas de todos os saltos envolvidos no fluxo de trabalho, iniciando a partir do EHR no ambiente de integridade do sistema, no parceiro de interoperabilidade e suas infra, incluindo o servidor FHIR e xadrez ao Office 365 ecossistema e Aplicativo de pacientes.

![Parceiros de interoperabilidade](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Introdução ao FHIR  

Se você não estiver familiarizado com FHIR e precisa de acesso fácil a um servidor de FHIR que você pode expor à interface de integração do Microsoft equipes EHR, Microsoft possui um servidor de FHIR de código aberto disponíveis para todos os desenvolvedores a usar. Consulte o artigo [o que é o servidor de FHIR para o Windows Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) para saber mais sobre a fonte open FHIR Server disponíveis na Microsoft e implantá-la para suas organizações.

Você também pode usar o ambiente de EHR seguro abrir HSPC para criar um um EHR que também dá suporte a um servidor de FHIR abrir e usar esse recurso para Familiarize-se com o aplicativo de pacientes. Recomendamos que você leia a [documentação de área restrita do HSPC](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox). Não apenas o modo seguro oferece uma fácil, interface do usuário orientada a e maneira simples de criação, adicionando e editando os pacientes, ele também oferece vários exemplos para começar.  

## <a name="enroll-in-the-private-preview"></a>Inscrever-se na visualização privada

Depois que você criou a fonte open FHIR Server, é realmente fácil para se conectar ao aplicativo pacientes dentro de seu locatário seguindo as etapas mencionadas a seguir:

1. [Entre em contato conosco](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview) com os seguintes detalhes iniciais:  
    - Seu nome 
    - Sua posição, 
    - A empresa ou organização que você representar
    - Por que você está interessado o aplicativo de pacientes para integração de EHR. 

    Iremos contatá-você assim que possível com mais de perguntas e orientá-lo um processo para fazer a instalação para a avaliação privada.

2. Certifique-se de que sideloading igual a custom apps é habilitado no inquilino onde você pretende testar o aplicativo de pacientes. Consulte [as políticas de permissão de aplicativo](../../admin-settings.md) para aprender a ativar isso do Centro de administração de equipes para o locatário do cliente ou a.

3. Sideload o aplicativo de pacientes manifesto que você obterá da Microsoft (depois que podemos processar seu email para nós) em uma equipe no locatário que será a ser usado para cenários de arredondamento de pacientes e coordenação de atendimento médico. As instruções detalhadas ao redor como carregar um aplicativo lado estão em [carregar um pacote de aplicativos para equipes da Microsoft](/microsoftteams/platform/concepts/apps/apps-upload)

4. Navegue até o canal geral de como o proprietário de equipe e, em seguida, clique na guia os pacientes. Você deverá ver uma experiência de execução primeira que apresentará duas opções, ou seja, modos de EHR e Manual. Selecione o **modo EHR** e copiar o ponto de extremidade do servidor de FHIR (que você tiver uma instalação apenas anteriormente com todos os dados necessários e os recursos pelas especificações acima) para o campo de Link e nomeie a conexão bem representando o servidor FHIR. Clique em conectar e tudo deve estar pronto para ir.

    ![Configurações do servidor de aplicativo de pacientes](../../media/patients-server.png)

5. Começar a usar o aplicativo para pesquisar os pacientes do servidor/EHR FHIR e adicioná-los a uma lista e por favor, [envie seus comentários](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback) se algo não está funcionando. Além disso, para estabelecer uma versão totalmente autenticada do aplicativo os pacientes- gt _ fluxo FHIR Server, por favor, entrem em caixa de diálogo offline com Microsoft Teams de engenharia de produto de saúde, pela solicitação de email mencionado anteriormente para esclarecer os requisitos e iremos ajuda a habilitar essa para você pelos requisitos de autenticação descritos acima do documento FHIR Interface.  


