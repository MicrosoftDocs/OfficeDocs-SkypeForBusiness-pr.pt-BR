---
title: Visão geral do aplicativo de pacientes
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
description: Saiba mais sobre como integrar registros de assistência médica eletrônica ao aplicativo Pacientes do Microsoft Teams usando APIs FHIR.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 594375959a8cd7cbbfc21c6b9d5ceb6c0f8a8dac
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803539"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Integração dos Registros Eletrônicos de Saúde no Microsoft Teams

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo Pacientes foi retirado e substituído pelo aplicativo [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Os dados do aplicativo Pacientes são armazenados na caixa de correio de grupo do grupo do Office 365 que faz o back-back da equipe. Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário. Os usuários podem criar suas listas de novo usando o [aplicativo Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Com as Listas, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam de reuniões de equipes de turnos e de atendimento a monitoramento geral de pacientes. Confira o modelo Pacientes em Listas para começar. Para saber mais sobre como gerenciar o aplicativo Listas em sua organização, consulte [Gerenciar o aplicativo Listas.](../../manage-lists-app.md)

Este artigo destina-se a um desenvolvedor geral de SERVIÇOS de SAÚDE interessado em usar APIs FHIR na parte superior de um sistema de informações médicas para se conectar ao Microsoft Teams. Isso habilitaria cenários de coordenação de atendimento que corresponderem às necessidades de uma organização de saúde.

Os artigos vinculados documentam as especificações de interface FHIR do aplicativo Pacientes do Microsoft Teams e as seções a seguir explicam o que é necessário para configurar um servidor FHIR e conectar-se ao aplicativo Pacientes em seu ambiente de desenvolvimento ou locatário. Você também precisará estar familiarizado com a documentação do servidor FHIR que você escolheu, que deve ser uma das opções com suporte:

- Datica (por meio de sua oferta [de CMI)](https://datica.com/compliant-managed-integration/)
- Infor Ltda (através da Ponte [Infor FHIR)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)
- Redox (por meio do [servidor R^FHIR)](https://www.redoxengine.com/fhir/)
- Dapasoft (por [meio deLalar em FHIR)](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)

> [!NOTE]
> Esse processo não inclui etapas que usam o centro de administração do Microsoft Teams ou cmdlets do PowerShell para habilitar recursos. A configuração é totalmente feita no lado do servidor/serviço FHIR e no cliente do aplicativo Pacientes.

Ilustrado abaixo está a arquitetura do aplicativo Pacientes:

![Diagrama da arquitetura do aplicativo Pacientes](../../media/patients-app-architecture.png)

As seções a seguir explicam os requisitos da camada de acesso de dados somente FHIR para o aplicativo Pacientes que um servidor FHIR (ou APIs FHR habilitadas para FHIR) devem atender para integrar-se ao aplicativo Pacientes, incluindo o seguinte:

- Expectativas em relação à autenticação do usuário
- Requisitos funcionais e técnicos da interface de integração
- Expectativas em relação ao desempenho e à confiabilidade
- Expectativas em torno dos recursos FHIR para serem suportados para o aplicativo Pacientes
- Processo de integração e o modelo de compromisso esperado
- Como começar a usar o FHIR e alguns desafios comuns com o aplicativo Pacientes
- Requisitos futuros para a próxima iteração do aplicativo Pacientes

> [!NOTE]
> Nas seções a seguir, a palavra "parceiro" ou "parceiro Interop" é usada para se referir a qualquer Organização de terceiros que permita a integração com sistemas EHR para o aplicativo Pacientes por meio de FHIR e está implementando um Servidor FHIR para corresponder às especificações listadas.

## <a name="functional-and-technical-requirements"></a>Requisitos técnicos e funcionais  

### <a name="authentication"></a>Autenticação  

A autorização  em nível de aplicativo sem suporte para autorização em nível de usuário é a maneira mais comumente suportada de realizar transformações de dados e expor conexões a dados de EHR por meio de FHIR, mesmo que o sistema EHR possa implementar a autorização no nível do usuário. O Serviço Interop (Parceiro) obtém acesso elevado aos dados de EHR e, quando eles expõem os mesmos dados que os recursos FHIR apropriados, não há contexto de autorização passado para o Consumidor do Serviço Interop (o aplicativo Pacientes) integrar com o Serviço ou Plataforma Interop. O aplicativo Pacientes não poderá impor a autorização no nível do usuário, mas dá suporte ao aplicativo para autenticação de aplicativos entre o aplicativo Pacientes e o serviço do parceiro Interop.

O modelo de autenticação de Aplicativo para Aplicativo é descrito abaixo:

A autenticação de serviço para serviço deve ser [](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)feita por meio do fluxo de Credenciais do Cliente OAuth 2.0. O serviço de parceiro precisa fornecer o seguinte:

1. O serviço Parceiro permite que o aplicativo Pacientes crie uma conta com o Parceiro, que permite que o aplicativo Pacientes gere e possui o client_id e o client_secret, gerenciados por meio de um portal de registro autenticado no servidor autenticação do parceiro.

2. O serviço parceiro é proprietário do sistema autenticação/autorização, que aceita e verifica (autentica) as credenciais do cliente fornecidas e fornece um token de acesso com dica de locatário no escopo, conforme descrito abaixo.

3. Por motivos de segurança ou em caso de violação secreta, o aplicativo Pacientes pode gerar o segredo e invalidar ou excluir o antigo segredo (exemplo do mesmo está disponível no Portal do Azure – Registro de Aplicativo do AAD).

4. O ponto de extremidade de metadados que hospeda a instrução de conformidade deve ser não autenticado, deve ser acessível sem token de autenticação.

5. O serviço parceiro fornece o ponto de extremidade de token para o aplicativo Pacientes solicitar um token de acesso usando um fluxo de credenciais do cliente. A URL do token conforme o servidor de autorização deve fazer parte da instrução de conformidade (recurso) FHIR buscada de metadados no servidor FHIR, como neste exemplo:

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

O serviço parceiro fornece o client_id e o client_secret para Pacientes, gerenciados por meio de um portal de registro Auth no lado do parceiro. O serviço parceiro fornece o ponto de extremidade para solicitar token de acesso usando um fluxo de credenciais do cliente. Uma resposta bem-sucedida deve incluir os token_type, access_token e expires_in parâmetros.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Roteamento: Mapeando o locatário do AAD para o ponto de extremidade do provedor

O aplicativo Pacientes conecta-se a um serviço de parceiro por meio de um único ponto de extremidade. O serviço de parceiro possui e mantém um mecanismo para mapear cada cliente da Microsoft (ID de Locatário do AAD) para um respectivo provedor de saúde (servidor FHIR) com o que o serviço de parceiro está trabalhando.

O mapeamento do locatário do AAD para um ponto de extremidade do provedor usa a ID de Locatário do AAD (GUID). O aplicativo Pacientes passa pela ID do Locatário no escopo, ao solicitar um token de acesso para cada solicitação. O serviço parceiro mantém o mapeamento da ID do Locatário para o ponto de extremidade do provedor e redireciona solicitações para um ponto de extremidade do provedor com base na ID do Locatário. Para fazer isso, o parceiro dá suporte à configuração em sua extremidade (manualmente ou por meio de um portal como parte da integração de organizações de provedores em sua Plataforma Interop).

O fluxo de trabalho Autenticação e Roteamento é mostrado abaixo:

![Diagrama do fluxo de trabalho Autenticação e Roteamento](../../media/Patient-app-6.png)

1. Solicite o token de acesso ao aplicativo enviando:
 
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

3. Solicite dados protegidos com o token do Access.

4. Mensagem de autorização: selecione o servidor FHIR apropriado para roteá-lo da ID do locatário no escopo.

5. Envia os dados protegidos do aplicativo do servidor FHIR autorizado após a autenticação com o token de aplicativo.

## <a name="interfaces"></a>Interfaces

Chamadas e campos específicos usados pelo aplicativo Pacientes são documentados nos artigos a seguir. Selecione a interface aplicável ao seu servidor FHIR/APIs FHIR.

- [Especificação de interface DSTU2](dstu2-interface.md)
- [Especificação de interface STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Desempenho e confiabilidade

Enquanto o aplicativo Pacientes está em visualização privada, não há garantias sobre o desempenho de ponta a ponta. Os fatores de desempenho incluem as latências relativas de todos os saltos envolvidos no fluxo de trabalho, começando pelo EHR no ambiente do sistema de saúde, até o parceiro Interop e seu infra, incluindo o Servidor FHIR e até o ecossistema e o aplicativo Pacientes do Office 365.

![Ilustração do desempenho dos parceiros Interop](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Começar a trabalhar com FHIR  

Se você for novo na FHIR e precisar de acesso fácil a um Servidor FHIR que possa expor à interface de integração do Microsoft Teams EHR, a Microsoft tem um servidor FHIR de código aberto disponível para todos os desenvolvedores usarem. Confira o artigo O que é o FHIR Server para [Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) para saber mais sobre o servidor FHIR de código aberto disponível na Microsoft e implantá-lo para suas organizações.

Você também pode usar o ambiente HSPC Open sandbox EHR para criar um EHR que também oferece suporte a um servidor FHIR aberto e usá-lo para brincar com o aplicativo Pacientes. Recomendamos que você leia a documentação [da área de trabalho HSPC.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox) Além de oferecer uma maneira fácil, voltada para a interface do usuário e fácil de criar, adicionar e editar Pacientes, a área de trabalho oferece várias amostras para começar. 
