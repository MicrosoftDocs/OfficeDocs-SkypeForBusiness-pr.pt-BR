---
title: Visão geral do aplicativo Pacientes
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Saiba mais sobre a integração de Registros Eletrônicos de Saúde no aplicativo Pacientes do Microsoft Teams usando APIs FHIR.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2b4878f67b7738a13e3c1385ee0713d6e3e3d481
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096205"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Integração dos Registros Eletrônicos de Saúde no Microsoft Teams

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo Pacientes será retirado e substituído pelo [aplicativo de Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Os dados do aplicativo Pacientes são armazenados na caixa de correio do grupo do Office 365 que apoia a equipe. Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário. Os usuários podem criar suas listas usando o [aplicativo Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Com o Lists, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam desde reuniões gerais com a equipe de atendimento até o monitoramento geral dos pacientes. Confira o modelo Pacientes no Lists para começar. Para saber mais sobre como gerenciar o aplicativo Lists em sua organização, consulte [Gerenciar o aplicativo Lists](../../manage-lists-app.md).

Este artigo destina-se a um desenvolvedor de IT de saúde geral interessado em usar APIs FHIR em cima de um sistema de informações médicas para se conectar ao Microsoft Teams. Isso habilitaria cenários de coordenação de cuidados que corresponderiam às necessidades de uma organização de saúde.

Os artigos vinculados documentam as especificações da interface FHIR para o aplicativo Pacientes do Microsoft Teams e as seções a seguir explicam o que é necessário para configurar um servidor FHIR e se conectar ao aplicativo Patients em seu ambiente de desenvolvimento ou locatário. Você também precisará estar familiarizado com a documentação do servidor FHIR escolhido, que deve ser uma das opções com suporte:

- Datica (por meio da oferta [de CMI)](https://datica.com/compliant-managed-integration/)
- Infor Cloverleaf (por meio da [Ponte Infor FHIR](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (por meio do [servidor R^FHIR](https://www.redoxengine.com/fhir/))
- Dapasoft (por [meio do Corolar em FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

> [!NOTE]
> Esse processo não inclui etapas que usam o centro de administração do Microsoft Teams ou cmdlets do PowerShell para habilitar recursos. A configuração é totalmente feita no lado servidor/serviço FHIR e no cliente de aplicativos Patients.

Ilustrado abaixo está a arquitetura do aplicativo Patients:

![Diagrama da arquitetura do aplicativo Patients](../../media/patients-app-architecture.png)

As seções a seguir explicam os requisitos da camada de acesso de dados somente FHIR para o aplicativo Patients que um servidor FHIR (ou APIs FHIR habilitados para EHR) deve atender para se integrar ao aplicativo Patients, incluindo o seguinte:

- Expectativas em torno da autenticação do usuário
- Requisitos funcionais e técnicos da interface de integração
- Expectativas em relação ao desempenho e confiabilidade
- Expectativas em torno dos recursos FHIR a serem suportados para o aplicativo Patients
- Processo de integração e o modelo de envolvimento esperado
- Como começar a usar o FHIR e alguns desafios comuns enfrentados com o aplicativo Patients
- Requisitos futuros para a próxima iteração do aplicativo Patients

> [!NOTE]
> Nas seções a seguir, a palavra "parceiro" ou "parceiro de interop" é usada para se referir a qualquer Organização de terceiros que habilita a integração aos sistemas EHR para o aplicativo Patients por meio de FHIR e está implementando um Servidor FHIR para corresponder às especificações listadas.

## <a name="functional-and-technical-requirements"></a>Requisitos funcionais e técnicos  

### <a name="authentication"></a>Autenticação  

A autorização  no nível do aplicativo sem suporte para autorização no nível do usuário é a maneira mais comumente suportada de realizar transformações de dados e expor conexões aos dados do EHR por meio de FHIR, mesmo que o sistema EHR possa implementar a autorização no nível do usuário. O Serviço de Interop (Parceiro) obtém acesso elevado aos dados do EHR e, quando eles expõem os mesmos dados dos recursos FHIR apropriados, não há contexto de autorização passado para o Consumidor de Serviço de Interop (o aplicativo Pacientes) integrando-se ao Serviço de Interop ou Plataforma. O aplicativo Patients não poderá impor a autorização no nível do usuário, mas dá suporte ao aplicativo para autenticação de aplicativos entre o aplicativo Patients e o serviço do parceiro de interop.

O modelo de autenticação Aplicativo para Aplicativo é descrito abaixo:

A autenticação de serviço para serviço deve ser [](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)feita por meio do fluxo de Credenciais do Cliente OAuth 2.0. O serviço parceiro precisa fornecer o seguinte:

1. O serviço parceiro permite que o aplicativo Pacientes crie uma conta com o Parceiro, que permite que o aplicativo Patients gere e gere e gere o client_id e o client_secret, gerenciados por meio de um portal de registro do Auth no servidor de Autenticação do parceiro.

2. O serviço parceiro é proprietário do sistema autenticação/autorização, que aceita e verifica (autentica) as credenciais do cliente fornecidas e fornece um token de acesso com dica de locatário no escopo, conforme descrito abaixo.

3. Por motivos de segurança ou em caso de violação secreta, o aplicativo Patients pode gerar o segredo e invalidar ou excluir o segredo antigo (exemplo do mesmo está disponível no Portal do Azure - Registro de Aplicativo do AAD).

4. O ponto de extremidade de metadados que hospeda a instrução de conformidade deve ser não autenticado, ele deve estar acessível sem token de autenticação.

5. O serviço parceiro fornece o ponto de extremidade de token para o aplicativo Patients solicitar um token de acesso usando um fluxo de credenciais do cliente. A URL de token como por servidor de autorização deve fazer parte da instrução FHIR conformance (capability) buscada de metadados no servidor FHIR, como neste exemplo:

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

Uma solicitação para um token de acesso consiste nos seguintes parâmetros:

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

O serviço parceiro fornece o client_id e client_secret para pacientes, gerenciado por meio de um portal de registro do Auth no lado do parceiro. O serviço parceiro fornece o ponto de extremidade para solicitar token de acesso usando um fluxo de credenciais do cliente. Uma resposta bem-sucedida deve incluir os parâmetros token_type, access_token e expires_in.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Roteamento: Mapeamento do Locatário AAD para o ponto de extremidade do provedor

O aplicativo Patients se conecta a um serviço de parceiro por meio de um único ponto de extremidade. O serviço parceiro possui e mantém um mecanismo para mapear cada cliente microsoft (ID de locatário do AAD) para um respectivo provedor de saúde (servidor FHIR) com o que o serviço parceiro está trabalhando.

O mapeamento do locatário do AAD para um ponto de extremidade do provedor usa a ID do Locatário AAD (GUID). O aplicativo Patients passa a ID do Locatário no escopo, ao solicitar um token de acesso para cada solicitação. O serviço parceiro mantém o mapeamento da ID do Locatário para o ponto de extremidade do Provedor e redireciona as solicitações para um ponto de extremidade do provedor com base na ID do locatário. Para fazer isso, o parceiro dá suporte à configuração no final (manualmente ou por meio de um portal como parte da integração das organizações de provedores à plataforma de interop).

O fluxo de trabalho de autenticação e roteamento é mostrado abaixo:

![Diagrama do fluxo de trabalho de Autenticação e Roteamento](../../media/Patient-app-6.png)

1. Solicitar token de acesso ao aplicativo enviando:
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. Responder com um token de aplicativo:

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. Solicitar dados protegidos com token do Access.

4. Mensagem de autorização: selecione o servidor FHIR apropriado a ser roteado para a partir da ID do locatário no escopo.

5. Envia os dados protegidos do aplicativo do servidor FHIR autorizado após a autenticação com o token de aplicativo.

## <a name="interfaces"></a>Interfaces

Chamadas e campos específicos usados pelo aplicativo Patients são documentados nos artigos a seguir. Selecione a interface aplicável às SUAS APIs FHIR server/FHIR.

- [Especificação de interface DSTU2](dstu2-interface.md)
- [Especificação de interface STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Desempenho e confiabilidade

Enquanto o aplicativo Patients estiver em visualização privada, não há garantias sobre o desempenho de ponta a ponta. Os fatores de desempenho incluem as latências relativas de todos os saltos envolvidos no fluxo de trabalho, começando pelo EHR no ambiente do sistema de saúde, até o parceiro de Interop e seu infra, incluindo o Servidor FHIR e até o ecossistema do Office 365 e o aplicativo Patients.

![Ilustração do desempenho de parceiros de interop](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Começar a trabalhar com FHIR  

Se você for novo no FHIR e precisar de acesso fácil a um FHIR Server que possa expor à interface de integração do Microsoft Teams EHR, a Microsoft terá um FHIR Server de código aberto disponível para todos os desenvolvedores usarem. Confira o artigo O que é O servidor FHIR para [o Azure](/azure/healthcare-apis/overview-open-source-server) para saber mais sobre o servidor FHIR de código aberto disponível da Microsoft e implantá-lo para suas organizações.

Você também pode usar o ambiente de EHR de área de área desamparada do HSPC Open para criar um EHR que também oferece suporte a um Servidor FHIR aberto e usá-lo para brincar com o aplicativo Patients. Recomendamos que você leia a documentação de [Área Desajuste HSPC](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox). Além de oferecer uma maneira fácil, orientada à interface do usuário e fácil de criar, adicionar e editar Pacientes, a área de segurança também oferece vários exemplos para começar.