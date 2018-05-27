solution

authors.component.ts

import { AuthorsService } from './../authors.service';
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'authors',
    template: `
      <h2>Angular</h2>
      <ul>
        <li *ngFor="let author of authors">
        {‌{ author }}
        </li>
      </ul>
    `
})
export class AuthorsComponent implements OnInit {
    authors;
  constructor(private authorsService: AuthorsService) { 
    this.authors = authorsService.getAuthors();
  }
  
  ngOnInit() {
  }

}

authors.service.ts
  
import { Injectable } from '@angular/core';
  
@Injectable()
export class AuthorsService {
  
  constructor() { }
  
  getAuthors() {
    return ["author1", "author2", "author3"];
  }

}

