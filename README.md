http://192.168.3.6:8070/tfs/DefaultCollection/LandT-Incentive-Platform/_git/LandT-Incentive-Platform


https://www.figma.com/proto/uont6pgOHwFh7aufjSU7gt/AMFI-Screens?node-id=211%3A8219&scaling=scale-down-width




```
readonly ROOT_URL: string = environment.baseURI;

  private handleError(error: HttpErrorResponse) {
    if (error.error instanceof ErrorEvent) {
      // A client-side or network error occurred. Handle it accordingly.
      console.error(
        'An error occurred:', error.error.message
      );
    } else {
      // The backend returned an unsuccessful response code.
      // The response body may contain clues as to what went wrong.
      console.error(
        `Backend returned code ${error.status}, ` +
        `body was: ${error.error.message}`
      );
    }
    // Return an observable with a user-facing error message.
    // return throwError('Something bad happened; please try again later.');
    return throwError(`Error: ${error.error.error}\nMessage: ${error.error.message}\nStatus: ${error.error.status}`);
  }

  get(url: string) {
    return this._http.get<any>(this.ROOT_URL + url).pipe(catchError(this.handleError));
  }

  post(url: string, object: any) {
    return this._http.post<any>(this.ROOT_URL + url, object).pipe(catchError(this.handleError));
  }
```
