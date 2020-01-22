### #2 Setting Typescript Up

##### 보다 정확한 정보는 tsconfig_option.md 확인. <br/>어느 블로그에서 자세히 설명해놓았더라.


```json
{
  "compilerOptions": { 
    "module": "commonjs",
    "target": "ES2015",
    "sourceMap": true
  },
  "include": ["index.ts"],
  "exclude": ["node_modules"]
}
```
- compilerOptions : node.js를 평범하게 사용하고 다양한걸 import 하거나 export 할 수 있게 만드는 것.
  - module : nodule 선택 (정확히는 모르겠음.)
  - target : 어떤 버전의 JavaScript로 컴파일 되고 싶은지 선택
  - sourceMap : sourceMap 처리를 하고 싶은지 알려줌

- include : 어떤 파일들이 컴파일 과정에 포함되는지 TypeScript에게 알려줌 컴파일 과정에서 포함할 파일의 배열을 적으면 됨
- exclude : include의 반대. 포함시키지 않을 파일의 배열



##### Typescript

- ts를 작성하고 터미널에 'tsc' 명령어를 작성하면 자동으로 map과 js파일을 생성한다.
  
  - 컴파일 후 실행하는 것은 불편하므로, package.json에 다음 script를 추가한다.
  
    > ```json
    > "scripts": {
    >     "start" : "node index.js",
    >     "prestart" : "tsc"
    >   }
    > ```
  
     이제 'yarn start'라는 명령어로 컴파일 후 실행이 가능해진다.
  
  - Node.js는 Typescript를 이해하지 못하기 떄문에 일반적인 javascript 코드로 컴파일하는 작업이 필요