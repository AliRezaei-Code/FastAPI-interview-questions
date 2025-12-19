![FastAPI Logo](raw.githubusercontent.com)

# FastAPI Interview Questions & Answers

A curated list of FastAPI interview questions based on the provided tutorial content. Covers setup, routing, validation, Pydantic, databases, WebSockets, and deployment.

### Table of Contents
1. [What is FastAPI and what is it used for?](#q1)
1. [What Python versions does FastAPI require?](#q2)
1. [Which two libraries is FastAPI built on top of?](#q3)
1. [What standards does FastAPI support out of the box?](#q4)
1. [What are the main benefits highlighted for FastAPI?](#q5)
1. [When was FastAPI created and by whom?](#q6)
1. [Why is FastAPI described as production-ready?](#q7)
1. [How does FastAPI performance compare to Node and Go?](#q8)
1. [How do you install FastAPI with pip?](#q9)
1. [Why do you need an ASGI server like Uvicorn?](#q10)
1. [How do you install Uvicorn (minimal vs standard)?](#q11)
1. [What extra capabilities come with Uvicorn standard install?](#q12)
1. [How can you verify installed packages and versions?](#q13)
1. [Why use a virtual environment for FastAPI?](#q14)
1. [What is the minimal FastAPI app structure?](#q15)
1. [What does `app = FastAPI()` represent?](#q16)
1. [How do you define a GET route for "/"?](#q17)
1. [What types can a path function return?](#q18)
1. [How do you start a dev server with reload?](#q19)
1. [What does the `--reload` flag do?](#q20)
1. [What is the purpose of the `/docs` endpoint?](#q21)
1. [Which UI does `/docs` use?](#q22)
1. [What does `/openapi.json` return?](#q23)
1. [How does FastAPI use JSON Schema?](#q24)
1. [What is `/redoc` used for?](#q25)
1. [What information appears in the OpenAPI schema?](#q26)
1. [What is Uvicorn and what standard does it implement?](#q27)
1. [Why are WSGI servers not suitable for async apps?](#q28)
1. [Which libraries does Uvicorn use under the hood?](#q29)
1. [How do you run Uvicorn from the command line?](#q30)
1. [How do you run Uvicorn programmatically?](#q31)
1. [Which CLI options are commonly used for host and port?](#q32)
1. [What problem do Python type hints solve in FastAPI?](#q33)
1. [How do you declare type hints for parameters?](#q34)
1. [How do you declare a return type hint?](#q35)
1. [Why can runtime TypeError still happen with type hints?](#q36)
1. [What is MyPy and how is it used?](#q37)
1. [How do typing.List and typing.Dict help with type hints?](#q38)
1. [How do type hints improve IDE autocomplete?](#q39)
1. [Why does typing a variable as str help method suggestions?](#q40)
1. [How do type hints help with user-defined classes?](#q41)
1. [How do type hints affect OpenAPI generation?](#q42)
1. [What is REST in the context of FastAPI?](#q43)
1. [What REST constraints are listed in the tutorial?](#q44)
1. [What advantages do REST constraints provide?](#q45)
1. [Which HTTP methods map to CRUD?](#q46)
1. [How does FastAPI expose resources?](#q47)
1. [What does statelessness mean in REST?](#q48)
1. [What is a path parameter?](#q49)
1. [How do you declare a path parameter in a route?](#q50)
1. [How do you access a path parameter in the function?](#q51)
1. [Can a route have multiple path parameters?](#q52)
1. [How do type hints validate path parameters?](#q53)
1. [What error occurs on type mismatch for path params?](#q54)
1. [How do path parameters differ from query parameters?](#q55)
1. [How does Swagger UI display path parameters?](#q56)
1. [How does FastAPI detect query parameters?](#q57)
1. [How do you define a route that uses only query params?](#q58)
1. [What is the URL format for query parameters?](#q59)
1. [Can you mix path and query parameters?](#q60)
1. [Where do query parameters appear in Swagger UI?](#q61)
1. [What happens when a required query parameter is missing?](#q62)
1. [How do you validate path parameters with Path?](#q63)
1. [How do you enforce min_length and max_length?](#q64)
1. [What numeric rules can Path enforce?](#q65)
1. [How do you validate query parameters with Query?](#q66)
1. [What does a validation error response include?](#q67)
1. [Why use `*` for keyword-only parameters with Path/Query?](#q68)
1. [How are validation rules shown in OpenAPI docs?](#q69)
1. [What is Pydantic used for in FastAPI?](#q70)
1. [How do you define a Pydantic model?](#q71)
1. [How does Pydantic handle type coercion?](#q72)
1. [What happens when Pydantic validation fails?](#q73)
1. [What is the Field class used for?](#q74)
1. [How do you convert a model to a dict?](#q75)
1. [What is `orm_mode` and why use it?](#q76)
1. [How do you accept a request body with Pydantic?](#q77)
1. [Which HTTP method is typical for request bodies?](#q78)
1. [How do you accept primitive body values with Body?](#q79)
1. [How do you combine path/query parameters with a body?](#q80)
1. [How does Swagger UI show request body schemas?](#q81)
1. [How does FastAPI serialize return values?](#q82)
1. [Can you return the same model you received?](#q83)
1. [How do you compute and return derived fields?](#q84)
1. [How do you return raw HTML from a route?](#q85)
1. [Which response class is used for HTML?](#q86)
1. [Which template engine is used in the tutorial?](#q87)
1. [How do you configure Jinja2Templates?](#q88)
1. [Why must the request be passed to TemplateResponse?](#q89)
1. [How do you insert variables in a Jinja2 template?](#q90)
1. [How do you pass a path parameter to a template?](#q91)
1. [What are static files in a FastAPI app?](#q92)
1. [Which library is required to serve static files?](#q93)
1. [How do you mount a static directory?](#q94)
1. [How do you reference static files in templates?](#q95)
1. [How do you include JavaScript from /static?](#q96)
1. [Why keep assets in static instead of templates?](#q97)
1. [How do you render an HTML form template?](#q98)
1. [Which HTTP method is used for form submission?](#q99)
1. [What is the role of the form enctype attribute?](#q100)
1. [How do you route a form action to a FastAPI endpoint?](#q101)
1. [Which FastAPI class parses form fields?](#q102)
1. [Which package is required for form parsing?](#q103)
1. [How do you declare form fields in a route?](#q104)
1. [What content type is used for form submissions?](#q105)
1. [Can you return a Pydantic model from form data?](#q106)
1. [How do you accept file uploads?](#q107)
1. [Which types are used for uploaded files?](#q108)
1. [How do you save an uploaded file to disk?](#q109)
1. [What form encoding is required for file uploads?](#q110)
1. [What does UploadFile provide compared to bytes?](#q111)
1. [What are cookies used for?](#q112)
1. [How do you set a cookie in FastAPI?](#q113)
1. [How do you read a cookie in FastAPI?](#q114)
1. [Where do cookie parameters show up in Swagger UI?](#q115)
1. [What happens if a cookie is missing?](#q116)
1. [How do you read a request header in FastAPI?](#q117)
1. [How are header names with hyphens handled?](#q118)
1. [How do you add custom headers to a response?](#q119)
1. [How do you set standard response headers?](#q120)
1. [Where can you see response headers in Swagger UI?](#q121)
1. [What is response_model used for?](#q122)
1. [How does response_model filter output fields?](#q123)
1. [How does response_model affect OpenAPI?](#q124)
1. [Can you return a larger object with a smaller response_model?](#q125)
1. [How does FastAPI validate response data?](#q126)
1. [How do you hide fields using response_model?](#q127)
1. [How do you define nested Pydantic models?](#q128)
1. [Can a model contain a list or tuple of other models?](#q129)
1. [How are nested models shown in Swagger UI?](#q130)
1. [How do nested models map to JSON?](#q131)
1. [Why use nested models?](#q132)
1. [What is dependency injection in FastAPI?](#q133)
1. [How does Depends reduce repeated parameters?](#q134)
1. [How do you create a dependency function?](#q135)
1. [How do you use a dependency in a route?](#q136)
1. [How do you implement dependencies as classes?](#q137)
1. [How do you declare decorator-level dependencies?](#q138)
1. [How do you use dependencies for validation?](#q139)
1. [Why use yield in a dependency?](#q140)
1. [What is CORS and why does it matter?](#q141)
1. [What is an origin?](#q142)
1. [How do you enable CORS in FastAPI?](#q143)
1. [What do allow_origins, allow_methods, allow_headers do?](#q144)
1. [What does CRUD stand for?](#q145)
1. [How do you implement CREATE with POST?](#q146)
1. [How do you implement READ all with GET?](#q147)
1. [How do you implement READ by id?](#q148)
1. [How do you implement UPDATE with PUT?](#q149)
1. [How do you implement DELETE with DELETE?](#q150)
1. [What are the limits of an in-memory list database?](#q151)
1. [Why use SQLAlchemy with FastAPI?](#q152)
1. [How do you create a SQLite engine?](#q153)
1. [What is a SQLAlchemy session?](#q154)
1. [What is declarative_base used for?](#q155)
1. [How do you define a SQLAlchemy model?](#q156)
1. [How do you create tables in the database?](#q157)
1. [How do you map Pydantic models to ORM models?](#q158)
1. [What is orm_mode in SQLAlchemy responses?](#q159)
1. [How do you add a record with a session?](#q160)
1. [How do you query records and return them?](#q161)
1. [Why use MongoDB with FastAPI?](#q162)
1. [Which Python driver is used for MongoDB?](#q163)
1. [How do you connect to MongoDB?](#q164)
1. [How do you insert a document into a collection?](#q165)
1. [How do you return a list of values with distinct?](#q166)
1. [How do you query a document by id?](#q167)
1. [What is GraphQL and why use it with FastAPI?](#q168)
1. [Which GraphQL library does the tutorial recommend?](#q169)
1. [How do you define Strawberry types and fields?](#q170)
1. [How do you mount a GraphQL app in FastAPI?](#q171)
1. [What endpoint provides the GraphiQL IDE?](#q172)
1. [What is a WebSocket and how is it different from HTTP?](#q173)
1. [How does FastAPI support WebSockets?](#q174)
1. [What is the basic WebSocket flow on the server?](#q175)
1. [How do you define a WebSocket route?](#q176)
1. [Why are WebSockets useful?](#q177)
1. [How do you connect to a WebSocket from the browser?](#q178)
1. [What does a simple echo WebSocket example do?](#q179)
1. [What are startup and shutdown events?](#q180)
1. [How do you register a startup handler?](#q181)
1. [How do you register a shutdown handler?](#q182)
1. [What are common uses for these handlers?](#q183)
1. [What is a sub-application in FastAPI?](#q184)
1. [How do you mount a sub-app?](#q185)
1. [How does routing work for a mounted sub-app?](#q186)
1. [Where are sub-app docs available?](#q187)
1. [What is middleware in FastAPI?](#q188)
1. [How do you create a custom middleware?](#q189)
1. [What does call_next do?](#q190)
1. [Name some built-in middleware.](#q191)
1. [When does middleware execute?](#q192)
1. [How do you mount a Flask app in FastAPI?](#q193)
1. [What is WSGIMiddleware used for?](#q194)
1. [What URL prefix is used for the Flask app?](#q195)
1. [Can FastAPI and Flask run side by side?](#q196)
1. [Why is deployment different from local dev?](#q197)
1. [What is Deta and how do you deploy to it?](#q198)
1. [What does `deta new` do?](#q199)
1. [Where can you access the deployed app and docs?](#q200)
1. [What is APIRouter and why use it in bigger FastAPI applications?](#q201)
1. [How do you include an APIRouter in the main FastAPI app?](#q202)
1. [How do you apply a common prefix, tags, responses, or dependencies when including a router?](#q203)
1. [In what order are router-level and decorator-level dependencies executed?](#q204)
1. [What does the status_code parameter in a path operation decorator do?](#q205)
1. [How do tags help API documentation, and how can you manage them consistently?](#q206)
1. [How can you add summary and description metadata to an endpoint?](#q207)
1. [How can you provide a description via the function docstring?](#q208)
1. [What does response_description control and what default is used if omitted?](#q209)
1. [How do you mark an endpoint as deprecated in FastAPI?](#q210)
1. [How do you change the response status code dynamically per request?](#q211)
1. [What is BackgroundTasks and when should you use it?](#q212)
1. [How do background tasks work across dependencies?](#q213)
1. [How do you raise an HTTP error in FastAPI, and what should detail contain?](#q214)
1. [How can you add custom headers to an HTTPException response?](#q215)
1. [How do you register a custom exception handler for your own exception type?](#q216)
1. [How do you override the RequestValidationError handler, and what caution applies?](#q217)
1. [What is jsonable_encoder and why is it useful for databases?](#q218)
1. [How do you implement partial updates with PATCH and exclude_unset?](#q219)
1. [What extra data types are supported by FastAPI/Pydantic and how are they serialized?](#q220)
1. [How do you group query parameters into a Pydantic model?](#q221)
1. [How do you forbid extra query parameters when using a model?](#q222)
1. [How do you declare header parameters with a Pydantic model and control underscore conversion?](#q223)
1. [Why might cookie parameter models not work when executing from Swagger UI?](#q224)
1. [How do you declare form fields with a Pydantic model?](#q225)
1. [What is response_class and how does it affect response encoding and docs?](#q226)
1. [When should you return a Response directly, and what do you lose by doing so?](#q227)
1. [How do you set response headers or cookies using a Response parameter?](#q228)
1. [How do you load settings from environment variables using Pydantic Settings?](#q229)
1. [How can you inject settings via a dependency to make testing easier?](#q230)
1. [How do you write async tests with HTTPX AsyncClient and pytest.anyio?](#q231)
1. [How do you enable trusted proxy headers and configure root_path behind a proxy?](#q232)
1. [How do you exclude unset/default/None fields from responses with response_model settings?](#q233)
1. [When would you access the Request object directly, and what is the tradeoff?](#q234)

<a id="q1"></a>
### 1. What is FastAPI and what is it used for?
FastAPI is a modern Python web framework for building APIs. It uses Python type hints for validation and automatic documentation. It is designed around ASGI for high concurrency and supports both async and sync endpoints.

<a id="q2"></a>
### 2. What Python versions does FastAPI require?
FastAPI requires Python 3.6 or above. Its core features rely on async/await and typing, so older Python versions are not supported.

<a id="q3"></a>
### 3. Which two libraries is FastAPI built on top of?
FastAPI is built on Starlette (ASGI framework) and Pydantic (data validation). Starlette handles routing, middleware, and networking while Pydantic handles parsing, validation, and schema generation.

<a id="q4"></a>
### 4. What standards does FastAPI support out of the box?
FastAPI is fully compatible with OpenAPI and JSON Schema standards. This enables automatic docs, client generation, and strong schema-based validation.

<a id="q5"></a>
### 5. What are the main benefits highlighted for FastAPI?
The tutorial highlights high performance, fast development speed, fewer human errors, and ease of learning. It also emphasizes automatic docs and strong IDE support via type hints.

<a id="q6"></a>
### 6. When was FastAPI created and by whom?
FastAPI was created by Sebastian Ramirez in December 2018. It was built to modernize Python API development with async support and type-driven validation.

<a id="q7"></a>
### 7. Why is FastAPI described as production-ready?
It supports API standards, provides strong validation, and is designed for reliable deployment, not just experimentation. Its ASGI foundation and tooling integration make it suitable for real production workloads.

<a id="q8"></a>
### 8. How does FastAPI performance compare to Node and Go?
The tutorial notes that FastAPI performance is on par with NodeJS and Go due to its ASGI foundation. Actual throughput depends on your server, I/O patterns, and implementation details.

<a id="q9"></a>
### 9. How do you install FastAPI with pip?
Use pip to install FastAPI:

```bash
pip3 install fastapi
```
You typically install it inside a virtual environment and pair it with an ASGI server like Uvicorn for local development.

<a id="q10"></a>
### 10. Why do you need an ASGI server like Uvicorn?
FastAPI does not include a built-in server. You run it with an ASGI server such as Uvicorn, which handles HTTP connections and the async event loop.

<a id="q11"></a>
### 11. How do you install Uvicorn (minimal vs standard)?
Minimal install:

```bash
pip3 install uvicorn
```

Standard install (adds extras):

```bash
pip3 install "uvicorn[standard]"
```
The standard extras bring in performance and protocol dependencies that are commonly used in production.

<a id="q12"></a>
### 12. What extra capabilities come with Uvicorn standard install?
The standard install adds WebSocket support and extra dependencies such as PyYAML. It also enables faster event loop and HTTP parsing options when available.

<a id="q13"></a>
### 13. How can you verify installed packages and versions?
Use `pip3 freeze` to list installed packages and versions. You can also use `pip show fastapi` or `pip list` for quick inspection.

<a id="q14"></a>
### 14. Why use a virtual environment for FastAPI?
A virtual environment isolates project dependencies and avoids conflicts with system packages. It also makes deployments more reproducible across machines.

<a id="q15"></a>
### 15. What is the minimal FastAPI app structure?
A minimal app imports FastAPI, creates an app instance, and defines a route:

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
async def index():
    return {"message": "Hello World"}
```
This is enough to serve JSON responses and verify your setup with an ASGI server.

<a id="q16"></a>
### 16. What does `app = FastAPI()` represent?
It creates the main ASGI application object that Uvicorn serves. This object holds routes, middleware, and dependency injection configuration.

<a id="q17"></a>
### 17. How do you define a GET route for "/"?
Use a decorator and a path operation function:

```python
@app.get("/")
async def index():
    return {"message": "Hello World"}
```
The decorator registers the function under the GET method for the given path.

<a id="q18"></a>
### 18. What types can a path function return?
It can return dict, list, str, int, or Pydantic model objects. FastAPI serializes them to JSON and can also accept Response objects for full control.

<a id="q19"></a>
### 19. How do you start a dev server with reload?
Run:

```bash
uvicorn main:app --reload
```
This is intended for local development and will restart the server when files change.

<a id="q20"></a>
### 20. What does the `--reload` flag do?
It enables auto-reload so code changes restart the server automatically. This uses file watching and should be disabled in production.

<a id="q21"></a>
### 21. What is the purpose of the `/docs` endpoint?
It provides interactive API documentation for your FastAPI app. The UI is generated from the OpenAPI schema.

<a id="q22"></a>
### 22. Which UI does `/docs` use?
FastAPI uses Swagger UI for the `/docs` endpoint. It is interactive and lets you try requests directly against your API.

<a id="q23"></a>
### 23. What does `/openapi.json` return?
It returns the generated OpenAPI schema in JSON format. The schema is built from your routes, parameters, and models at runtime.

<a id="q24"></a>
### 24. How does FastAPI use JSON Schema?
JSON Schema is used to describe the request and response data structures inside OpenAPI. This drives validation, docs, and client generation.

<a id="q25"></a>
### 25. What is `/redoc` used for?
`/redoc` provides an alternative documentation UI based on ReDoc. It is primarily for browsing, not for interactive testing.

<a id="q26"></a>
### 26. What information appears in the OpenAPI schema?
It includes API title, version, paths, operations, and response schemas. It can also include components, parameters, tags, and security definitions.

<a id="q27"></a>
### 27. What is Uvicorn and what standard does it implement?
Uvicorn is an ASGI server that runs async Python web apps. It implements the ASGI spec so frameworks like FastAPI can handle concurrency efficiently.

<a id="q28"></a>
### 28. Why are WSGI servers not suitable for async apps?
WSGI is synchronous and cannot efficiently handle async tasks or WebSockets. It typically relies on threads or processes, which limits scalability for I/O-bound workloads.

<a id="q29"></a>
### 29. Which libraries does Uvicorn use under the hood?
The tutorial mentions uvloop for the event loop and httptools for HTTP. These provide faster async I/O and HTTP parsing compared to pure-Python defaults.

<a id="q30"></a>
### 30. How do you run Uvicorn from the command line?
Example:

```bash
uvicorn main:app --reload
```
This points to the module and app instance, and is the typical way to run in development.

<a id="q31"></a>
### 31. How do you run Uvicorn programmatically?
Call `uvicorn.run()` in your script:

```python
if __name__ == "__main__":
    uvicorn.run("main:app", host="127.0.0.1", port=8000, reload=True)
```
This is useful for embedding the server in a Python entrypoint or custom startup script.

<a id="q32"></a>
### 32. Which CLI options are commonly used for host and port?
Use `--host` and `--port`, for example `--host 127.0.0.1 --port 8000`. You can also configure workers, log level, and reload behavior via CLI options.

<a id="q33"></a>
### 33. What problem do Python type hints solve in FastAPI?
Type hints document expected types, enable validation, and improve tooling support. FastAPI reads them to generate schemas and error responses automatically.

<a id="q34"></a>
### 34. How do you declare type hints for parameters?
Use annotations after parameter names:

```python
def division(x: int, y: int):
    return x / y
```
FastAPI uses these annotations to parse inputs and reject invalid values.

<a id="q35"></a>
### 35. How do you declare a return type hint?
Add `-> type` before the colon:

```python
def division(x: int, y: int) -> float:
    return x / y
```
Return type hints help with editor tooling and can be used by FastAPI for response documentation.

<a id="q36"></a>
### 36. Why can runtime TypeError still happen with type hints?
Python does not enforce hints at runtime, so invalid types can still raise errors unless validated. FastAPI relies on Pydantic to enforce types at request time.

<a id="q37"></a>
### 37. What is MyPy and how is it used?
MyPy is a static type checker. Run `mypy your_file.py` to catch type mismatches before runtime, often as part of CI.

<a id="q38"></a>
### 38. How do typing.List and typing.Dict help with type hints?
They let you specify element types, such as `List[str]` or `Dict[str, int]`. This improves validation and schema generation for nested structures.

<a id="q39"></a>
### 39. How do type hints improve IDE autocomplete?
IDEs can suggest methods and detect errors based on the declared type. They also enable static analysis and refactoring support.

<a id="q40"></a>
### 40. Why does typing a variable as str help method suggestions?
With `name: str`, the IDE knows it is a string and suggests string methods like `capitalize()`. This reduces mistakes and speeds up development.

<a id="q41"></a>
### 41. How do type hints help with user-defined classes?
If a parameter is typed as a class, the IDE can autocomplete its attributes and methods. This also helps type checkers ensure correct usage across modules.

<a id="q42"></a>
### 42. How do type hints affect OpenAPI generation?
FastAPI uses type hints to build request/response schemas for OpenAPI. The generated schema feeds Swagger UI and client code generation tools.

<a id="q43"></a>
### 43. What is REST in the context of FastAPI?
REST is a resource-based architecture for web APIs using HTTP methods for operations. It emphasizes predictable URLs, statelessness, and uniform interfaces.

<a id="q44"></a>
### 44. What REST constraints are listed in the tutorial?
- Uniform interface
- Statelessness
- Client-server
- Cacheability
- Layered system
- Code on demand
These are the classic REST constraints that guide API design and scalability.

<a id="q45"></a>
### 45. What advantages do REST constraints provide?
They enable scalability, simplicity, modifiability, reliability, portability, and visibility. They also support caching and loose coupling between client and server.

<a id="q46"></a>
### 46. Which HTTP methods map to CRUD?
POST = Create, GET = Read, PUT = Update, DELETE = Delete. PATCH is commonly used for partial updates.

<a id="q47"></a>
### 47. How does FastAPI expose resources?
Resources are exposed through path operations and HTTP methods. Each path operation maps to a handler function with typed parameters.

<a id="q48"></a>
### 48. What does statelessness mean in REST?
Each request must contain all the information needed for processing, without server-side session state. Authentication data is typically sent on every request.

<a id="q49"></a>
### 49. What is a path parameter?
A path parameter is a variable part of a URL path, such as `{name}`. It is required for the route to match.

<a id="q50"></a>
### 50. How do you declare a path parameter in a route?
Use braces in the path string:

```python
@app.get("/hello/{name}")
async def hello(name: str):
    return {"name": name}
```
FastAPI matches the placeholder name to the function argument and validates it using the type hint.

<a id="q51"></a>
### 51. How do you access a path parameter in the function?
Define a function argument with the same name as the path parameter. FastAPI injects the converted value automatically.

<a id="q52"></a>
### 52. Can a route have multiple path parameters?
Yes, for example `/hello/{name}/{age}`. Each placeholder must be unique and will be validated independently.

<a id="q53"></a>
### 53. How do type hints validate path parameters?
Type hints like `age: int` force conversion and validation for that parameter. Invalid values result in a 422 validation error before your handler runs.

<a id="q54"></a>
### 54. What error occurs on type mismatch for path params?
FastAPI returns a validation error with details such as `type_error.integer`. The response includes the field location and message.

<a id="q55"></a>
### 55. How do path parameters differ from query parameters?
Path parameters are part of the URL path, while query parameters follow `?` in the URL. Path params are required; query params are optional unless declared required.

<a id="q56"></a>
### 56. How does Swagger UI display path parameters?
Swagger UI lists path parameters as required inputs for the endpoint. It shows their names, types, and constraints from your annotations.

<a id="q57"></a>
### 57. How does FastAPI detect query parameters?
Any function parameter not declared in the path is treated as a query parameter. Defaults make them optional; missing required values trigger validation errors.

<a id="q58"></a>
### 58. How do you define a route that uses only query params?
Example:

```python
@app.get("/hello")
async def hello(name: str, age: int):
    return {"name": name, "age": age}
```
Both values are taken from the query string and converted to the declared types.

<a id="q59"></a>
### 59. What is the URL format for query parameters?
Use `?key=value` pairs joined by `&`, for example `/hello?name=Ravi&age=20`. Values arrive as strings and are converted by FastAPI.

<a id="q60"></a>
### 60. Can you mix path and query parameters?
Yes. Example: `/hello/{name}` plus query parameters like `?age=20`. This is common for filtering or pagination.

<a id="q61"></a>
### 61. Where do query parameters appear in Swagger UI?
They appear under the Parameters section for the endpoint. Swagger UI marks them as required or optional based on defaults.

<a id="q62"></a>
### 62. What happens when a required query parameter is missing?
FastAPI returns a 422 validation error with a `detail` section. The response includes the missing field location and a human-readable message.

<a id="q63"></a>
### 63. How do you validate path parameters with Path?
Use the Path class:

```python
from fastapi import Path

@app.get("/hello/{name}")
async def hello(name: str = Path(..., min_length=3, max_length=10)):
    return {"name": name}
```
Path lets you add constraints and metadata to path parameters that appear in docs and validation errors.

<a id="q64"></a>
### 64. How do you enforce min_length and max_length?
Pass `min_length` and `max_length` to Path or Field for string parameters. These constraints are enforced before your handler runs.

<a id="q65"></a>
### 65. What numeric rules can Path enforce?
Use `gt`, `ge`, `lt`, and `le` for numeric ranges. `gt/lt` are strict, while `ge/le` are inclusive bounds.

<a id="q66"></a>
### 66. How do you validate query parameters with Query?
Use the Query class:

```python
from fastapi import Query

@app.get("/report")
async def report(percent: float = Query(..., ge=0, le=100)):
    return {"percent": percent}
```
Query provides the same validation and metadata features as Path for query parameters.

<a id="q67"></a>
### 67. What does a validation error response include?
It includes `detail` with fields like `loc`, `msg`, and `type`. This structure makes it easy to identify which input failed validation.

<a id="q68"></a>
### 68. Why use `*` for keyword-only parameters with Path/Query?
It forces keyword-only arguments so FastAPI can parse them correctly when using Path and Query together. This avoids ambiguity with positional arguments.

<a id="q69"></a>
### 69. How are validation rules shown in OpenAPI docs?
Swagger UI lists constraints such as min/max length or numeric ranges. These are derived from your Path/Query/Field metadata.

<a id="q70"></a>
### 70. What is Pydantic used for in FastAPI?
It validates and parses request bodies and response data using type hints. Pydantic also powers schema generation for OpenAPI.

<a id="q71"></a>
### 71. How do you define a Pydantic model?
Example:

```python
from pydantic import BaseModel
from typing import List

class Student(BaseModel):
    id: int
    name: str
    subjects: List[str] = []
```
Pydantic models provide defaults, validation, and helpful error messages for invalid input.

<a id="q72"></a>
### 72. How does Pydantic handle type coercion?
It converts compatible types, such as a numeric string to an int, when possible. You can opt into stricter validation in newer Pydantic versions.

<a id="q73"></a>
### 73. What happens when Pydantic validation fails?
It raises a ValidationError with details about the failed fields. FastAPI catches this and returns a structured 422 response.

<a id="q74"></a>
### 74. What is the Field class used for?
Field adds metadata and validation rules like max_length or titles to model fields. It can also define defaults, examples, and descriptions.

<a id="q75"></a>
### 75. How do you convert a model to a dict?
Call `.dict()` on the model instance. In Pydantic v2, the equivalent method is `.model_dump()`.

<a id="q76"></a>
### 76. What is `orm_mode` and why use it?
`orm_mode = True` allows Pydantic models to read ORM objects directly. This lets you return ORM instances and still get proper serialization.

<a id="q77"></a>
### 77. How do you accept a request body with Pydantic?
Declare the model as a function parameter:

```python
@app.post("/students/")
async def student_data(s1: Student):
    return s1
```
FastAPI reads the JSON body, validates it against the model, and injects a typed instance.

<a id="q78"></a>
### 78. Which HTTP method is typical for request bodies?
POST is typically used to send JSON request bodies. PUT and PATCH also commonly include request bodies for updates.

<a id="q79"></a>
### 79. How do you accept primitive body values with Body?
Use the Body class:

```python
from fastapi import Body

@app.post("/students")
async def student_data(name: str = Body(...), marks: int = Body(...)):
    return {"name": name, "marks": marks}
```
Body marks these values as coming from the request body instead of the query string.

<a id="q80"></a>
### 80. How do you combine path/query parameters with a body?
Add them all to the function signature, for example:

```python
@app.post("/students/{college}")
async def student_data(college: str, age: int, student: Student):
    return {"college": college, "age": age, **student.dict()}
```
FastAPI pulls each value from the correct location and validates them independently.

<a id="q81"></a>
### 81. How does Swagger UI show request body schemas?
It displays a Request body section with the JSON schema for the model. This includes required fields, types, and example structure when provided.

<a id="q82"></a>
### 82. How does FastAPI serialize return values?
It converts them to JSON automatically, including Pydantic models. Internally it uses a JSON-compatible encoder to handle types like datetime.

<a id="q83"></a>
### 83. Can you return the same model you received?
Yes. If you return the model instance, FastAPI serializes it back to JSON. You can still apply response_model filtering to remove sensitive fields.

<a id="q84"></a>
### 84. How do you compute and return derived fields?
Compute values inside the function before returning, such as adding a percentage field. You can also define optional fields in the response model for derived values.

<a id="q85"></a>
### 85. How do you return raw HTML from a route?
Return an HTMLResponse with HTML content. You can also set `response_class=HTMLResponse` on the decorator.

<a id="q86"></a>
### 86. Which response class is used for HTML?
Use `fastapi.responses.HTMLResponse`. It sets the Content-Type to `text/html` for proper rendering.

<a id="q87"></a>
### 87. Which template engine is used in the tutorial?
The tutorial uses Jinja2 for templating. It supports template inheritance, filters, and server-side rendering.

<a id="q88"></a>
### 88. How do you configure Jinja2Templates?
Example:

```python
from fastapi.templating import Jinja2Templates

templates = Jinja2Templates(directory="templates")
```
This sets the folder where your HTML templates live and enables template loading.

<a id="q89"></a>
### 89. Why must the request be passed to TemplateResponse?
Jinja2Templates requires the request object for context and URL generation. It enables helpers like `url_for` inside templates.

<a id="q90"></a>
### 90. How do you insert variables in a Jinja2 template?
Use `{{ variable_name }}` in the HTML. Jinja2 will render values from the context dictionary you pass.

<a id="q91"></a>
### 91. How do you pass a path parameter to a template?
Provide it in the TemplateResponse context:

```python
return templates.TemplateResponse("hello.html", {"request": request, "name": name})
```
All context values are available in the template as Jinja2 variables.

<a id="q92"></a>
### 92. What are static files in a FastAPI app?
Static files are assets such as images, CSS, and JavaScript that do not change per request. They are served directly without template rendering.

<a id="q93"></a>
### 93. Which library is required to serve static files?
You need `aiofiles` to serve static files with FastAPI. It provides async file I/O used by StaticFiles.

<a id="q94"></a>
### 94. How do you mount a static directory?
Example:

```python
from fastapi.staticfiles import StaticFiles

app.mount("/static", StaticFiles(directory="static"), name="static")
```
Mounting creates a sub-application that serves files under the `/static` URL path.

<a id="q95"></a>
### 95. How do you reference static files in templates?
Use `url_for`:

```html
<img src="{{ url_for('static', path='fa-logo.png') }}" />
```
Using `url_for` keeps paths correct if your app is mounted under a prefix.

<a id="q96"></a>
### 96. How do you include JavaScript from /static?
Use a script tag with `url_for`:

```html
<script src="{{ url_for('static', path='hello.js') }}"></script>
```
This ensures the correct URL is generated in different environments.

<a id="q97"></a>
### 97. Why keep assets in static instead of templates?
Static assets are served unchanged and are easier to cache and manage separately. Templates remain focused on dynamic HTML rendering.

<a id="q98"></a>
### 98. How do you render an HTML form template?
Create a GET route that returns a TemplateResponse for the form HTML. Use a separate POST route to handle submission.

<a id="q99"></a>
### 99. Which HTTP method is used for form submission?
POST is commonly used to submit form data. GET is used for retrieving the form, not sending the form body.

<a id="q100"></a>
### 100. What is the role of the form enctype attribute?
It selects the encoding. Use `multipart/form-data` for file uploads and the default for plain text fields.

<a id="q101"></a>
### 101. How do you route a form action to a FastAPI endpoint?
Set the form `action` to the POST endpoint URL you define in FastAPI. Ensure the form `method` matches your route and consider using `url_for` in templates.

<a id="q102"></a>
### 102. Which FastAPI class parses form fields?
Use `fastapi.Form` to parse form fields. It tells FastAPI to read fields from form-encoded bodies.

<a id="q103"></a>
### 103. Which package is required for form parsing?
Install `python-multipart`. It is required for parsing both standard form data and file uploads.

<a id="q104"></a>
### 104. How do you declare form fields in a route?
Example:

```python
from fastapi import Form

@app.post("/submit/")
async def submit(nm: str = Form(...), pwd: str = Form(...)):
    return {"username": nm}
```
Using `Form(...)` makes the fields required; defaults make them optional.

<a id="q105"></a>
### 105. What content type is used for form submissions?
Standard form submissions use `application/x-www-form-urlencoded`. File uploads require `multipart/form-data`.

<a id="q106"></a>
### 106. Can you return a Pydantic model from form data?
Yes. You can build a model from the form fields and return it as response_model. This keeps validation and response serialization consistent.

<a id="q107"></a>
### 107. How do you accept file uploads?
Use `UploadFile` and `File` in the endpoint signature. This tells FastAPI to parse multipart form data and provide a file object.

<a id="q108"></a>
### 108. Which types are used for uploaded files?
`UploadFile = File(...)` is the common pattern in FastAPI. You can also use `bytes` for small files, but it loads the whole file into memory.

<a id="q109"></a>
### 109. How do you save an uploaded file to disk?
Example:

```python
import shutil

with open("destination.png", "wb") as buffer:
    shutil.copyfileobj(file.file, buffer)
```
`UploadFile` exposes a file-like object so you can stream to disk without loading everything into RAM.

<a id="q110"></a>
### 110. What form encoding is required for file uploads?
The form must use `enctype="multipart/form-data"`. Without it, the file field will not be parsed correctly.

<a id="q111"></a>
### 111. What does UploadFile provide compared to bytes?
It provides a file-like object and metadata like filename. It also supports streaming and spooling to disk for large files.

<a id="q112"></a>
### 112. What are cookies used for?
Cookies store small pieces of data on the client for later requests. They are commonly used for sessions, preferences, or tracking.

<a id="q113"></a>
### 113. How do you set a cookie in FastAPI?
Example:

```python
response.set_cookie(key="username", value="admin")
```
You typically set cookies on a `Response` object so they are sent in the final response headers.

<a id="q114"></a>
### 114. How do you read a cookie in FastAPI?
Use Cookie dependency:

```python
from fastapi import Cookie

async def read_cookie(username: str = Cookie(None)):
    return {"username": username}
```
If no default is provided, the cookie becomes required and missing values will trigger a 422 error.

<a id="q115"></a>
### 115. Where do cookie parameters show up in Swagger UI?
They appear as parameters for the endpoint when Cookie is used. Swagger UI shows their names, types, and required status.

<a id="q116"></a>
### 116. What happens if a cookie is missing?
The parameter value is None if you provide a default of None. If the cookie is required, FastAPI returns a 422 validation error.

<a id="q117"></a>
### 117. How do you read a request header in FastAPI?
Use the Header dependency:

```python
from fastapi import Header

async def read_header(accept_language: str = Header(None)):
    return {"Accept-Language": accept_language}
```
Header parameters are case-insensitive and converted to valid Python identifiers.

<a id="q118"></a>
### 118. How are header names with hyphens handled?
Hyphens are converted to underscores in parameter names (accept-language -> accept_language). You can use the `alias` parameter if you need a specific header name.

<a id="q119"></a>
### 119. How do you add custom headers to a response?
Return a JSONResponse with a headers dict:

```python
return JSONResponse(content=data, headers={"X-Web-Framework": "FastAPI"})
```
You can also set headers on a `Response` parameter for the same effect.

<a id="q120"></a>
### 120. How do you set standard response headers?
Provide them in the headers dict, for example `Content-Language`. The same approach works for both custom and standard headers.

<a id="q121"></a>
### 121. Where can you see response headers in Swagger UI?
In the response section under Headers after executing the endpoint. You only see them after clicking "Execute" in the docs.

<a id="q122"></a>
### 122. What is response_model used for?
It defines the shape of the response and validates output data. It is also used to filter out any fields not declared in the model.

<a id="q123"></a>
### 123. How does response_model filter output fields?
Only fields defined in the response_model are included in the response. Extra keys are removed before sending the response.

<a id="q124"></a>
### 124. How does response_model affect OpenAPI?
It generates the response schema for the endpoint in OpenAPI docs. This drives documentation and client generation.

<a id="q125"></a>
### 125. Can you return a larger object with a smaller response_model?
Yes. FastAPI will filter the output to the response_model fields. This is a common way to hide sensitive data.

<a id="q126"></a>
### 126. How does FastAPI validate response data?
It validates that the returned data conforms to the response_model types. If it does not, FastAPI raises a server error because the backend returned invalid data.

<a id="q127"></a>
### 127. How do you hide fields using response_model?
Return a full model but set response_model to a smaller one that excludes sensitive fields. This keeps internal fields out of responses without changing business logic.

<a id="q128"></a>
### 128. How do you define nested Pydantic models?
Use another BaseModel as a field type in your model. Pydantic will validate nested objects recursively.

<a id="q129"></a>
### 129. Can a model contain a list or tuple of other models?
Yes. Use List[Model] or Tuple[Model] to define nested collections. This maps cleanly to arrays in JSON.

<a id="q130"></a>
### 130. How are nested models shown in Swagger UI?
They appear as separate schemas with references in the parent schema. Swagger UI lets you drill into each component model.

<a id="q131"></a>
### 131. How do nested models map to JSON?
They produce nested JSON objects and arrays that mirror the model structure. This keeps complex payloads organized and predictable.

<a id="q132"></a>
### 132. Why use nested models?
They keep complex data organized and validated at each level. Nested models also improve reusability across endpoints.

<a id="q133"></a>
### 133. What is dependency injection in FastAPI?
It is a mechanism to provide shared logic or resources to multiple routes. Dependencies can be sync or async and are resolved per request.

<a id="q134"></a>
### 134. How does Depends reduce repeated parameters?
It moves common parameters into a shared dependency function or class. This centralizes validation and reduces boilerplate in handlers.

<a id="q135"></a>
### 135. How do you create a dependency function?
Example:

```python
async def dependency(id: str, name: str, age: int):
    return {"id": id, "name": name, "age": age}
```
Dependencies can also perform side effects or raise HTTPException when validation fails.

<a id="q136"></a>
### 136. How do you use a dependency in a route?
Use Depends in the function signature:

```python
@app.get("/user/")
async def user(dep: dict = Depends(dependency)):
    return dep
```
FastAPI resolves the dependency before calling the path operation function.

<a id="q137"></a>
### 137. How do you implement dependencies as classes?
Define a class with __init__ and use it with Depends:

```python
class Dependency:
    def __init__(self, id: str, name: str, age: int):
        self.id = id
        self.name = name
        self.age = age
```
Class-based dependencies can hold state per request and support complex initialization logic.

<a id="q138"></a>
### 138. How do you declare decorator-level dependencies?
Use the dependencies parameter on the decorator:

```python
@app.get("/user/", dependencies=[Depends(validate)])
```
These run even if their return values are not used by the handler.

<a id="q139"></a>
### 139. How do you use dependencies for validation?
A dependency can raise HTTPException when data is invalid. This is a clean way to enforce auth or business rules across routes.

<a id="q140"></a>
### 140. Why use yield in a dependency?
Use yield to provide a resource and perform cleanup afterward (for example, closing a DB session). Code after the yield runs even if the request fails.

<a id="q141"></a>
### 141. What is CORS and why does it matter?
CORS controls whether browsers can call your API from different origins. It affects preflight requests and is critical for frontend-backend integrations.

<a id="q142"></a>
### 142. What is an origin?
An origin is the combination of protocol, domain, and port. If any of these differ, the request is cross-origin.

<a id="q143"></a>
### 143. How do you enable CORS in FastAPI?
Add CORSMiddleware:

```python
from fastapi.middleware.cors import CORSMiddleware

app.add_middleware(
    CORSMiddleware,
    allow_origins=["http://localhost"],
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
```
These settings control which browsers can access your API and what headers they can send.

<a id="q144"></a>
### 144. What do allow_origins, allow_methods, allow_headers do?
They define which origins, HTTP methods, and headers are permitted. You can also set `allow_credentials` and `expose_headers` for advanced cases.

<a id="q145"></a>
### 145. What does CRUD stand for?
Create, Read, Update, Delete. These map to standard HTTP methods in REST APIs.

<a id="q146"></a>
### 146. How do you implement CREATE with POST?
Use a POST route to append an item to storage (for example, a list). It commonly returns the created resource with status 201.

<a id="q147"></a>
### 147. How do you implement READ all with GET?
Define a GET route that returns the full list of items. In practice, you often add pagination and filtering.

<a id="q148"></a>
### 148. How do you implement READ by id?
Use a GET route with a path parameter and return the matching item. If the item is missing, return a 404 error.

<a id="q149"></a>
### 149. How do you implement UPDATE with PUT?
Use a PUT route with a path parameter to replace an item in storage. PUT typically replaces the resource, not just part of it.

<a id="q150"></a>
### 150. How do you implement DELETE with DELETE?
Use a DELETE route with a path parameter to remove an item. Common responses are 204 No Content or the deleted resource.

<a id="q151"></a>
### 151. What are the limits of an in-memory list database?
It is not persistent and is not safe for concurrent or multi-process use. Data resets on restart and does not scale across workers.

<a id="q152"></a>
### 152. Why use SQLAlchemy with FastAPI?
SQLAlchemy provides ORM support to map Python classes to SQL tables. It also manages sessions, queries, and transactions across databases.

<a id="q153"></a>
### 153. How do you create a SQLite engine?
Example:

```python
from sqlalchemy import create_engine

engine = create_engine("sqlite:///./test.db", connect_args={"check_same_thread": False})
```
The connect_args flag is needed for SQLite when using multiple threads.

<a id="q154"></a>
### 154. What is a SQLAlchemy session?
A session is the database handle used to run queries and transactions. It manages the unit of work and commits changes to the database.

<a id="q155"></a>
### 155. What is declarative_base used for?
It creates the base class for defining ORM models. All mapped classes inherit from this base to share metadata.

<a id="q156"></a>
### 156. How do you define a SQLAlchemy model?
Declare a class with __tablename__ and Column fields. Columns define types, constraints, and primary keys.

<a id="q157"></a>
### 157. How do you create tables in the database?
Call `Base.metadata.create_all(bind=engine)`. In production you typically use migrations rather than auto-creation.

<a id="q158"></a>
### 158. How do you map Pydantic models to ORM models?
Create a Pydantic model with matching fields and enable orm_mode. This allows reading ORM instances via attribute access.

<a id="q159"></a>
### 159. What is orm_mode in SQLAlchemy responses?
It allows Pydantic models to read ORM objects directly. That makes response serialization work without manual dict conversion.

<a id="q160"></a>
### 160. How do you add a record with a session?
Create an ORM instance, add it, commit, and refresh it. Refreshing loads generated fields like primary keys.

<a id="q161"></a>
### 161. How do you query records and return them?
Use `db.query(Model).all()` or `filter(...).first()` and return the results. In production you usually map ORM results to Pydantic response models.

<a id="q162"></a>
### 162. Why use MongoDB with FastAPI?
MongoDB is a schema-less document store that fits flexible JSON-style data. It is useful when your data shape evolves frequently or is highly nested.

<a id="q163"></a>
### 163. Which Python driver is used for MongoDB?
The tutorial uses PyMongo. For async access in FastAPI, Motor is the common alternative.

<a id="q164"></a>
### 164. How do you connect to MongoDB?
Create a client with `MongoClient()`. You pass a connection string and then select a database and collection.

<a id="q165"></a>
### 165. How do you insert a document into a collection?
Example:

```python
result = book_collection.insert_one(book.dict())
```
The result object includes the inserted ID, which you can return or store.

<a id="q166"></a>
### 166. How do you return a list of values with distinct?
Use `collection.distinct("field")`. You can also pass a filter to limit which documents are considered.

<a id="q167"></a>
### 167. How do you query a document by id?
Use `find_one({"bookID": id})` or similar filters. If you use MongoDB's `_id`, you may need to convert to/from ObjectId.

<a id="q168"></a>
### 168. What is GraphQL and why use it with FastAPI?
GraphQL provides a single endpoint and allows clients to request only the data they need. This can reduce overfetching and improve frontend flexibility.

<a id="q169"></a>
### 169. Which GraphQL library does the tutorial recommend?
The tutorial recommends Strawberry. It offers a Pythonic, type-annotated API that integrates with FastAPI.

<a id="q170"></a>
### 170. How do you define Strawberry types and fields?
Decorate classes and methods:

```python
@strawberry.type
class Book:
    title: str

@strawberry.type
class Query:
    @strawberry.field
    def book(self) -> Book:
        return Book(title="Computer Fundamentals")
```
Type annotations define the schema, and `@strawberry.field` marks resolver functions.

<a id="q171"></a>
### 171. How do you mount a GraphQL app in FastAPI?
Create a schema and mount it:

```python
graphql_app = GraphQL(schema)
app.add_route("/book", graphql_app)
app.add_websocket_route("/book", graphql_app)
```
The websocket route enables subscriptions if your GraphQL setup supports them.

<a id="q172"></a>
### 172. What endpoint provides the GraphiQL IDE?
The GraphiQL IDE is available at the GraphQL route, such as `/book`. It provides an in-browser query editor and explorer.

<a id="q173"></a>
### 173. What is a WebSocket and how is it different from HTTP?
WebSockets provide persistent, full-duplex communication over a single TCP connection, unlike HTTP request/response. They keep a connection open for real-time messaging.

<a id="q174"></a>
### 174. How does FastAPI support WebSockets?
FastAPI provides a WebSocket class and a websocket route decorator. Under the hood it uses Starlette's WebSocket implementation.

<a id="q175"></a>
### 175. What is the basic WebSocket flow on the server?
Accept the connection, receive text, and send responses in a loop. You should also handle disconnects to clean up resources.

<a id="q176"></a>
### 176. How do you define a WebSocket route?
Example:

```python
from fastapi import WebSocket

@app.websocket("/ws")
async def websocket_endpoint(websocket: WebSocket):
    await websocket.accept()
    while True:
        data = await websocket.receive_text()
        await websocket.send_text(f"Message text was: {data}")
```
You must call `await websocket.accept()` before reading or writing messages.

<a id="q177"></a>
### 177. Why are WebSockets useful?
They enable real-time updates such as chat, live notifications, and streaming data. They reduce latency by avoiding repeated HTTP polling.

<a id="q178"></a>
### 178. How do you connect to a WebSocket from the browser?
Use JavaScript:

```javascript
var ws = new WebSocket("ws://localhost:8000/ws");
ws.send("hello");
```
Use `wss://` in production when your site is served over HTTPS.

<a id="q179"></a>
### 179. What does a simple echo WebSocket example do?
It sends back the same message it receives, often prefixed with a label. This is a basic way to verify bidirectional communication.

<a id="q180"></a>
### 180. What are startup and shutdown events?
They are lifecycle hooks that run when the application starts or stops. They are typically used to initialize or clean up shared resources.

<a id="q181"></a>
### 181. How do you register a startup handler?
Use the decorator:

```python
@app.on_event("startup")
async def startup_event():
    ...
```
Startup handlers are executed once when the application process starts.

<a id="q182"></a>
### 182. How do you register a shutdown handler?
Use the decorator:

```python
@app.on_event("shutdown")
async def shutdown_event():
    ...
```
Shutdown handlers run during graceful shutdown to release resources.

<a id="q183"></a>
### 183. What are common uses for these handlers?
Initialize resources on startup and clean them up on shutdown. Common examples include DB connections, caches, and background schedulers.

<a id="q184"></a>
### 184. What is a sub-application in FastAPI?
A sub-application is another FastAPI app mounted under a path in a main app. It can have its own routes, middleware, and docs.

<a id="q185"></a>
### 185. How do you mount a sub-app?
Use `app.mount("/subapp", subapp)`. The sub-app will handle all requests under that prefix.

<a id="q186"></a>
### 186. How does routing work for a mounted sub-app?
Requests under the mount path are handled by the sub-app's routes. The main app does not see those requests.

<a id="q187"></a>
### 187. Where are sub-app docs available?
They appear under the mount path, for example `/subapp/docs`. Each sub-app generates its own OpenAPI schema.

<a id="q188"></a>
### 188. What is middleware in FastAPI?
Middleware is code that runs for every request and response. It is commonly used for logging, security headers, and metrics.

<a id="q189"></a>
### 189. How do you create a custom middleware?
Use the `@app.middleware("http")` decorator:

```python
@app.middleware("http")
async def addmiddleware(request: Request, call_next):
    response = await call_next(request)
    return response
```
Custom middleware can inspect or modify the request and response objects.

<a id="q190"></a>
### 190. What does call_next do?
It forwards the request to the next handler and returns the response. This is how middleware passes control down the stack.

<a id="q191"></a>
### 191. Name some built-in middleware.
CORSMiddleware, HTTPSRedirectMiddleware, TrustedHostMiddleware, and GZipMiddleware. The order you add middleware affects execution order.

<a id="q192"></a>
### 192. When does middleware execute?
It runs before the route handler and after the handler returns a response. Middleware layers wrap each other in the order they are added.

<a id="q193"></a>
### 193. How do you mount a Flask app in FastAPI?
Wrap the Flask app with WSGIMiddleware and mount it on a path. This lets you serve legacy WSGI apps inside an ASGI stack.

<a id="q194"></a>
### 194. What is WSGIMiddleware used for?
It adapts a WSGI app (Flask/Django) to run under an ASGI server. This enables interoperability between async and sync frameworks.

<a id="q195"></a>
### 195. What URL prefix is used for the Flask app?
Whatever prefix you pass to mount, such as `/flask`. The WSGI app only handles routes under that prefix.

<a id="q196"></a>
### 196. Can FastAPI and Flask run side by side?
Yes. Each app runs under its own route prefix. FastAPI can serve ASGI routes while WSGI routes are bridged via middleware.

<a id="q197"></a>
### 197. Why is deployment different from local dev?
Production deployment requires a public endpoint and a hosting platform, not just a local Uvicorn process. You also need process management, logging, security, and scaling concerns.

<a id="q198"></a>
### 198. What is Deta and how do you deploy to it?
Deta is a cloud platform with a CLI. You log in and deploy with `deta new`, which provisions a micro and uploads your code.

<a id="q199"></a>
### 199. What does `deta new` do?
It creates a new micro, installs dependencies, and deploys your app to an endpoint. It also generates a live URL for the service.

<a id="q200"></a>
### 200. Where can you access the deployed app and docs?
Use the endpoint URL given by Deta, and add `/docs` for Swagger UI. The OpenAPI schema is at `/openapi.json`.

<a id="q201"></a>
### 201. What is APIRouter and why use it in bigger FastAPI applications?
APIRouter is a router class for grouping related endpoints in separate modules. It acts like a mini FastAPI app so you can keep routes organized, reuse prefixes, tags, responses, and dependencies, and then include them in the main app. This keeps large projects maintainable and avoids duplicated configuration.

<a id="q202"></a>
### 202. How do you include an APIRouter in the main FastAPI app?
Create a router in a module, define routes on it, import it in main, and call `app.include_router(router)`. The router routes are added to the application and appear in the OpenAPI docs. You can include the same router multiple times with different prefixes if needed.

<a id="q203"></a>
### 203. How do you apply a common prefix, tags, responses, or dependencies when including a router?
Set those options in the APIRouter constructor or pass them to `app.include_router(...)`. Prefixes should not end with a trailing slash, and the options apply to every route in that router. This is useful when you include routers you do not control.

<a id="q204"></a>
### 204. In what order are router-level and decorator-level dependencies executed?
Router-level dependencies run first, then dependencies declared in the path operation decorator, and then parameter dependencies. All dependencies are resolved before the endpoint function runs. FastAPI also caches dependency results per request by default.

<a id="q205"></a>
### 205. What does the status_code parameter in a path operation decorator do?
It sets the default HTTP status code for successful responses and documents it in OpenAPI. You can pass an int or constants from `fastapi.status` or `http.HTTPStatus`. You can still override it dynamically via a Response parameter.

<a id="q206"></a>
### 206. How do tags help API documentation, and how can you manage them consistently?
Tags group endpoints in the interactive docs and OpenAPI. You can pass `tags=[...]`, and for consistency you can define tags in an Enum or constants. This keeps large APIs navigable in Swagger and ReDoc.

<a id="q207"></a>
### 207. How can you add summary and description metadata to an endpoint?
Use `summary=` and `description=` on the path operation decorator. These values show up in OpenAPI and Swagger UI and help clarify endpoint intent.

<a id="q208"></a>
### 208. How can you provide a description via the function docstring?
Write a docstring inside the path operation function and FastAPI will use it as the description. Markdown in the docstring is rendered in the docs and can span multiple lines.

<a id="q209"></a>
### 209. What does response_description control and what default is used if omitted?
It sets the response description in OpenAPI. If omitted, FastAPI uses a default like "Successful response". OpenAPI requires every response to have a description.

<a id="q210"></a>
### 210. How do you mark an endpoint as deprecated in FastAPI?
Pass `deprecated=True` to the path operation decorator. The docs UI will mark the endpoint as deprecated but it will still work.

<a id="q211"></a>
### 211. How do you change the response status code dynamically per request?
Accept a `Response` parameter and set `response.status_code` inside the function. You can still return normal data and keep response_model filtering. Dependencies can also set the status code, with the last one winning.

<a id="q212"></a>
### 212. What is BackgroundTasks and when should you use it?
BackgroundTasks lets you schedule work to run after the response is sent. Use it for small side effects like emails or logging that should not block the response. For heavy jobs, use a task queue like Celery.

<a id="q213"></a>
### 213. How do background tasks work across dependencies?
Declare `BackgroundTasks` in dependencies or sub-dependencies; FastAPI reuses the same instance and aggregates tasks. All added tasks run after the response is sent, in the order they were added.

<a id="q214"></a>
### 214. How do you raise an HTTP error in FastAPI, and what should detail contain?
Raise `HTTPException(status_code=..., detail=...)`. The detail can be any JSON-serializable data and becomes the error response body. Raising the exception stops further processing.

<a id="q215"></a>
### 215. How can you add custom headers to an HTTPException response?
Pass a `headers` dict when raising `HTTPException`. This is useful for auth challenges or rate limit hints like `WWW-Authenticate`.

<a id="q216"></a>
### 216. How do you register a custom exception handler for your own exception type?
Use `@app.exception_handler(CustomError)` and return a response, commonly a `JSONResponse`. The handler receives the `Request` and the exception instance. This lets you centralize error formatting.

<a id="q217"></a>
### 217. How do you override the RequestValidationError handler, and what caution applies?
Register a handler with `@app.exception_handler(RequestValidationError)` to customize validation output. Avoid leaking internal file or line details when returning errors to clients, especially in production.

<a id="q218"></a>
### 218. What is jsonable_encoder and why is it useful for databases?
`jsonable_encoder` converts Pydantic models and complex types (like datetime) into JSON-compatible data structures. It returns Python objects ready for JSON serialization or storage in JSON-based databases. This is commonly used before writing to NoSQL stores.

<a id="q219"></a>
### 219. How do you implement partial updates with PATCH and exclude_unset?
Use a model with optional fields and call `model.model_dump(exclude_unset=True)` (or `.dict()` in Pydantic v1) to get only provided values. Merge into the stored model with `model_copy(update=...)` and save the result. This prevents default values from overwriting existing data.

<a id="q220"></a>
### 220. What extra data types are supported by FastAPI/Pydantic and how are they serialized?
FastAPI supports UUID, datetime/date/time, timedelta, Decimal, bytes, sets, and more. They parse from strings and serialize to JSON-friendly formats like ISO 8601 strings, floats, or lists. This lets you use rich types in signatures without manual parsing.

<a id="q221"></a>
### 221. How do you group query parameters into a Pydantic model?
Define a Pydantic model and declare it with `Annotated[Model, Query()]` in the endpoint signature. FastAPI pulls each field from the query string and validates it. This is useful when many query params belong together.

<a id="q222"></a>
### 222. How do you forbid extra query parameters when using a model?
Set the model config to forbid extra fields (for example `extra = "forbid"`). Extra query parameters will produce a 422 validation error. This enforces strict API contracts.

<a id="q223"></a>
### 223. How do you declare header parameters with a Pydantic model and control underscore conversion?
Use `Annotated[HeaderModel, Header()]` for grouped headers. To keep underscores, pass `Header(convert_underscores=False)`, noting some proxies reject underscores. This is useful when integrating with nonstandard headers.

<a id="q224"></a>
### 224. Why might cookie parameter models not work when executing from Swagger UI?
Browsers restrict JavaScript from setting arbitrary cookies, so the docs UI may not send them. The cookies still appear in docs, but execution can fail without real browser cookies. Use a real browser session or a tool like curl to test.

<a id="q225"></a>
### 225. How do you declare form fields with a Pydantic model?
Create a Pydantic model and declare it with `Annotated[Model, Form()]` in the endpoint. FastAPI extracts form fields into the model and validates them. This requires `python-multipart` to be installed.

<a id="q226"></a>
### 226. What is response_class and how does it affect response encoding and docs?
`response_class` lets you choose the Response subclass in the decorator, which sets the media type and OpenAPI docs. JSON response classes still apply response_model filtering to returned data. It is useful for HTML, streaming, or optimized JSON responses.

<a id="q227"></a>
### 227. When should you return a Response directly, and what do you lose by doing so?
Return a Response directly when you need full control over headers, cookies, media type, or streaming. You bypass response_model filtering and automatic OpenAPI documentation for that response. You must ensure content and headers are correct yourself.

<a id="q228"></a>
### 228. How do you set response headers or cookies using a Response parameter?
Accept a `Response` parameter and set headers or cookies on it, such as `response.headers[...]` or `response.set_cookie(...)`. FastAPI merges those into the final response while still serializing your returned data. Dependencies can also set these values.

<a id="q229"></a>
### 229. How do you load settings from environment variables using Pydantic Settings?
Create a Settings class that inherits from `BaseSettings` (from `pydantic_settings`) and instantiate it. Pydantic reads env vars, parses types, and can also load from a `.env` file. This keeps secrets out of source code.

<a id="q230"></a>
### 230. How can you inject settings via a dependency to make testing easier?
Provide a `get_settings` dependency that returns a Settings instance (often cached with `lru_cache`) and use it with Depends. In tests, override the dependency to supply test settings. This avoids global state and improves test isolation.

<a id="q231"></a>
### 231. How do you write async tests with HTTPX AsyncClient and pytest.anyio?
Mark tests with `@pytest.mark.anyio`, create an `httpx.AsyncClient(app=app, base_url="http://test")`, and `await` requests. Use a lifespan manager if your tests need startup or shutdown events. This mirrors real async behavior more closely than TestClient.

<a id="q232"></a>
### 232. How do you enable trusted proxy headers and configure root_path behind a proxy?
Run the server with `--forwarded-allow-ips` to trust `X-Forwarded-*` headers so redirects and URLs use the public scheme and host. Use `--root-path` when a proxy strips a prefix so OpenAPI and docs point to the correct path. This is common behind Nginx or Traefik.

<a id="q233"></a>
### 233. How do you exclude unset/default/None fields from responses with response_model settings?
Use `response_model_exclude_unset`, `response_model_exclude_defaults`, or `response_model_exclude_none` in the decorator. These control which fields are omitted during response serialization. This is useful for sparse models and large payloads.

<a id="q234"></a>
### 234. When would you access the Request object directly, and what is the tradeoff?
Access `Request` when you need raw request details like client host or the full body. The tradeoff is that data read directly is not validated or documented by FastAPI. Use this sparingly and validate manually if needed.
